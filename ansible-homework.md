cat > ~/ansible-homework/README.md << 'EOF'
# Домашнее задание по Ansible

Студент: [Ваше Имя Фамилия]  
Курс: Администрирование Linux  
Дата сдачи: 05.02.2026

---

## 📋 Содержание
- [Задание 1: Три плейбука](#задание-1-три-плейбука)
  - [1.1 Скачивание и распаковка Kafka](#11-скачивание-и-распаковка-kafka)
  - [1.2 Установка tuned](#12-установка-tuned)
  - [1.3 Изменение MOTD с переменной](#13-изменение-motd-с-переменной)
- [Задание 2: Динамический MOTD](#задание-2-динамический-motd)
- [Задание 3: Роль для Apache](#задание-3-роль-для-apache)
- [Структура проекта](#структура-проекта)
- [Как запустить](#как-запустить)

---

## Задание 1: Три плейбука

### 1.1 Скачивание и распаковка Kafka

**Файл:** [`playbooks/kafka_download.yml`](playbooks/kafka_download.yml)

```yaml
---
- name: Download and unpack Apache Kafka archive
  hosts: all
  become: yes
  vars:
    kafka_version: "3.6.1"
    download_url: "https://archive.apache.org/dist/kafka/{{ kafka_version }}/kafka_2.13-{{ kafka_version }}.tgz"
    download_dest: "/tmp/kafka_{{ kafka_version }}.tgz"
    extract_path: "/opt/kafka"

  tasks:
    - name: Install required packages for Debian/Ubuntu
      apt:
        name: 
          - wget
          - tar
          - gzip
        state: present
        update_cache: no
      when: ansible_os_family == "Debian"

    - name: Create directory for extraction
      file:
        path: "{{ extract_path }}"
        state: directory
        owner: root
        group: root
        mode: '0755'

    - name: Download Kafka archive
      get_url:
        url: "{{ download_url }}"
        dest: "{{ download_dest }}"
        mode: '0644'
      register: download_result
      until: download_result is succeeded
      retries: 3
      delay: 5

    - name: Extract Kafka archive
      unarchive:
        src: "{{ download_dest }}"
        dest: "{{ extract_path }}"
        remote_src: yes
        creates: "{{ extract_path }}/kafka_2.13-{{ kafka_version }}"
