University: ITMO University

Faculty: FTMI

Course: Cloud platforms as the basis of technology entrepreneurship

Year: 2024

Group: U4225

Author: Kolevatykh Nikita Alexandrovich

Lab: Lab1

Date of create: 21.10.2024

Date of finished: 22.10.2024

1. Создал Service Account с ролью Storage Admin
![image](https://github.com/user-attachments/assets/729ffebb-d668-4fbd-a59b-6974b35c7b40)

2. Создал минимальный compute engine с Machine type e2-micro в режиме spot
![image](https://github.com/user-attachments/assets/1d91993b-bca2-4a70-ab25-f2503b78e50c)

3. С помощью утилиты gsutils нашел бакет lab1-bucket-itmo и скопировал 3 файла в локальную папку на VM
![image](https://github.com/user-attachments/assets/c66a8f1b-fb2f-4e05-90a2-5c72e40491ba)

4. Поменял права доступа для service account с Storage Admin на Compute Viewer
![image](https://github.com/user-attachments/assets/f3e5100a-99d4-44df-8cad-677d62b62198)

5. Результат: из-за смены прав невозможно увидеть или скопировать файлы
