# Домашнее задание к занятию "`Ansible. Часть 2`" - `Захаров Иван`


`Выполните действия, приложите файлы с плейбуками и вывод выполнения.`

файлы с плейбуками

[kafka_download.yml](https://raw.githubusercontent.com/kinnwailos/homework-assignment-Zakharov-Ivan/refs/heads/main/playbooks/kafka_download.yml)

[tuned_setup.yml](https://raw.githubusercontent.com/kinnwailos/homework-assignment-Zakharov-Ivan/refs/heads/main/playbooks/tuned_setup.yml)

[motd_setup.yml](https://raw.githubusercontent.com/kinnwailos/homework-assignment-Zakharov-Ivan/refs/heads/main/playbooks/motd_setup.yml)

``
вывод выполнения

[kafka.txt](https://raw.githubusercontent.com/kinnwailos/homework-assignment-Zakharov-Ivan/refs/heads/main/output/kafka.txt)

[motd.txt](https://raw.githubusercontent.com/kinnwailos/homework-assignment-Zakharov-Ivan/refs/heads/main/output/motd.txt)

[tuned.txt](https://raw.githubusercontent.com/kinnwailos/homework-assignment-Zakharov-Ivan/refs/heads/main/output/tuned.txt)

``


<img width="809" height="573" alt="{513F4611-5663-4F0D-8140-0B7C4BEBA26A}" src="https://github.com/user-attachments/assets/c9f5b92d-ea03-4f6e-bb7d-35bfaea3b2fa" />



---

### Задание 2


`Выполните действия, приложите файлы с модифицированным плейбуком и вывод выполнения.`

файлы 


[motd_dynamic.yml](https://raw.githubusercontent.com/kinnwailos/homework-assignment-Zakharov-Ivan/refs/heads/main/playbooks/motd_dynamic.yml)


[motd_dynamic.j2](https://raw.githubusercontent.com/kinnwailos/homework-assignment-Zakharov-Ivan/refs/heads/main/templates/motd_dynamic.j2)


вывод


[motd_dynamic.txt](https://raw.githubusercontent.com/kinnwailos/homework-assignment-Zakharov-Ivan/refs/heads/main/output/motd_dynamic.txt)




<img width="1274" height="579" alt="{9ADBC020-03C7-4167-B2B4-FA04ADC501CD}" src="https://github.com/user-attachments/assets/c37521b9-2d8f-47d1-8a30-b4d67cbf1e28" />


---


### Задание 3


`Приведите ответ в свободной форме........`

## Задание 3: Роль для Apache

✅ Выполнено успешно  
📁 Плейбук: [`playbooks/deploy_webserver.yml`](playbooks/deploy_webserver.yml)  
📁 Структура роли: [`roles/webserver/`](roles/webserver/)  
📄 Вывод: [`output/webserver.txt`](output/webserver.txt)  
📸 Веб-страница: ![](screenshots/04_webpage.png)  
📸 Проверка curl: ![](screenshots/05_curl_check.png)

### Проверка доступности сайта
```bash
$ curl -I http://localhost
HTTP/1.1 200 OK
Server: Apache/2.4.58 (Ubuntu)
```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`



