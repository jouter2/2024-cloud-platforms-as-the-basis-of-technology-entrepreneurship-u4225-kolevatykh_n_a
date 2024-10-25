University: ITMO University

Faculty: FTMI

Course: Cloud platforms as the basis of technology entrepreneurship

Year: 2024

Group: U4225

Author: Kolevatykh Nikita Alexandrovich

Lab: Lab2

Date of create: 25.10.2024

Date of finished: 25.10.2024

1. Создал Cloud Run из представленного дефолтного сервиса Hello. 
![image](https://github.com/user-attachments/assets/fae21670-9401-4d6b-941e-bbcc2ba99e4b)

2. Перешел по ссылке предоставленной Cloud Run и протестировал сервис.
![image](https://github.com/user-attachments/assets/43f47a48-a3ae-4f98-8ecf-b00a023acf06)

3. Перешел в разделы метрики:
![image](https://github.com/user-attachments/assets/4e01bab1-1a1e-43ce-b6a1-4dbf2a32032d)
![image](https://github.com/user-attachments/assets/39bb2bb0-11f6-4ea7-98bc-b62bad05819b)
![image](https://github.com/user-attachments/assets/b3140f5f-f43e-4d2b-af7c-bf5fe68da486)
![image](https://github.com/user-attachments/assets/ec665f39-9e95-4075-9671-edf8d612a2b2)
![image](https://github.com/user-attachments/assets/1f9919b3-b5b4-4924-925e-555441c1fda7)
Метрики показывают различные стандартные параметры контейнера, такие как: число запросов, задержка запросов, подсчет инстанций контейнера, сколько памяти использует контейнер и так далее.

5. Перешел в разделы логи:
![image](https://github.com/user-attachments/assets/7173609c-a892-4b14-bda2-ac12eb892310)
- В начале система создает новый сервис в Cloud Run с именем "kolevatykhlab2". Это сопровождается записями типа Services.CreateService, что означает успешное создание сервиса.
- Затем отмечается событие создания новой инстанции (контейнера). Причина — OVERFLOW, что указывает на необходимость запуска дополнительной инстанции из-за нехватки текущих ресурсов для обработки трафика. Это нормальная ситуация, когда контейнеры автоматически масштабируются в зависимости от нагрузки.
- После этого контейнер был успешно запущен, о чем говорит сообщение Hello from Cloud Run!, а также указано, что контейнер ожидает HTTP-запросов на порту 8080. Лог показывает, что контейнер начал прослушивать порт 8080, а также произошло успешное подключение через протокол TCP на этот порт.
- После запуска контейнера система начала обрабатывать HTTP-запросы (метод GET) с клиента Chrome. Время ответа на каждый запрос было достаточно быстрым (6-7 мс), что свидетельствует о нормальной работе сервиса и адекватном времени отклика.

6. Изменил ваш Cloud Run, поменяв порт на 8090. Попробуйте попереключать трафик между версиями, сравните результаты работы.
![image](https://github.com/user-attachments/assets/b8b60320-af17-44ea-bfb1-e4943db95476)
- Контейнер снова успешно запустился, что подтверждается сообщением Hello from Cloud Run!. Контейнер теперь прослушивает HTTP-запросы на порту 8090. Это указывает на то, что конфигурация порта была изменена, и сервис начал работать на новом порту.
- Далее TCP probe прошел успешно с первой попытки. Это означает, что система проверила доступность контейнера на новом порту 8090, и контейнер ответил корректно на проверку. Это стандартная процедура проверки того, что контейнер готов к работе.
- Затем логи показывают операцию ReplaceService, что означает, что Cloud Run заменяет старый сервис на новый с обновленными конфигурациями. Это подтверждает, что сервис был перезапущен с изменениями, которые включают новый порт 8090.
- Последняя запись указывает на то, что контейнер успешно обработал HTTP-запрос от браузера Chrome. Как и в предыдущем случае, запрос был выполнен быстро (4 мс), что указывает на корректную работу сервиса на новом порту.

**Вывод: изменение порта на 8090 прошло успешно.**
Система запустила контейнер с новой конфигурацией порта, проверила его доступность через TCP, и контейнер начал обслуживать HTTP-запросы. Операция замены сервиса (ReplaceService) также выполнена корректно. Логи показывают нормальную работу сервиса без каких-либо ошибок.