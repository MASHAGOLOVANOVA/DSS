# **Практическая работа №1**

## 1. **Async**


   
   Было применены async методы для обращения к базе данных.
   Async методы позволяют выполнять параллельные запросы, которые улучшают производительность системы.
   
   Для реализации методов использовалось встроенная библиотека goroutines, позволяющая ассинхронно запускать задачи.
   В данный момент реализована ассинхронность только для репозитория account_repository (В плане расширить на другие репозитории).

   Интеграция с Telegram, в виде чат-бота, позволит пользоваться системой через популярный мессенджер,
   благодаря чему можно будет с удобством пользоваться системой через мобильные устройства.
   
   Репо: https://github.com/MASHAGOLOVANOVA/mvp-2-spms
   
   ПР: https://github.com/MASHAGOLOVANOVA/mvp-2-spms/pull/1

## 2. **СУБД**
  В рамках практики 0 была выбрана MySQL исходя из следующих факторов:
  1. СУБД очень популярная, есть много гайдов и хорошая документация.
  2. СУБД поддерживает ассинхронные операции.
  3. СУБД совместима с Go, есть много библиотек для внедрения MySQL в свой проект, например gorm, которая как раз используется в проекте.
  4. У этого разработчика есть опыт работы с этой СУБД, а значит разработка пойдет быстрее.

  СУБД подключена через gorm.

 ![image](https://github.com/user-attachments/assets/64714088-6e64-4c1a-a654-01be06d54c35)


## 3. **Слои системы**

  Листинг по ссылке: https://github.com/MASHAGOLOVANOVA/mvp-2-spms/blob/dss-practice1/main/web_server/cmd/web_app/web_app.go
   
  
  3.1.	Фреймворк

  Был выбран Chi. Причины:
  3.1.1. Он легкий и хорошо подходит небольшим приложениям.
  3.1.2. Middleware для логирования и аутентификации.

  ![image](https://github.com/user-attachments/assets/8ffd92c9-0ec5-4735-b0e5-c452bba40fed)

  3.1.3. Группировка маршрутов - полезно для организации кода.

 ![image](https://github.com/user-attachments/assets/0f92951e-f91b-4cb0-bda6-f7b0af99c25e)

    
  3.2.	Application
  
  Для обработки входящих запросов

  ![image](https://github.com/user-attachments/assets/8376e8c3-138a-4fd8-8587-fd8d063551c4)


  3.3.	Domain

  Для бизнес-логики

  ![image](https://github.com/user-attachments/assets/9a86eb5b-2605-4858-b0c6-bfab6fa44de6)

  
  3.4.	Инфраструктура

  Для обращения к бд

  ![image](https://github.com/user-attachments/assets/54df5c7a-2cec-4eca-84a4-7b1ff7d033d6)

## 4. **Тесты**

  Были обновлены, поскольлку была добавлена ассинхронная обработка обращений к бд.

  МР:

  Скрины проходки тестов обновленных:

![image](https://github.com/user-attachments/assets/f92907ee-fe16-4f81-8e18-2a07cfac3023)

![image](https://github.com/user-attachments/assets/82e7e122-8eb5-40bf-a486-0b2996b17c0f)

![image](https://github.com/user-attachments/assets/0ec2ce6d-34e4-4754-8372-b11683c7adfd)

![image](https://github.com/user-attachments/assets/03d48037-344b-4ff5-9ea3-a300843b2a25)

## 5. **Docker**

Были написаны докер файлы для запуска базы данных (+ тестовой) и веб-сервера, лежат в основной директории проекта

Демонстрация работы проекта с запущенным ботом

![image](https://github.com/user-attachments/assets/42572845-86cd-43bb-a0fb-494a67a8b32e)

Демонстрация работы проекта с веб-клиента

![image](https://github.com/user-attachments/assets/aed76a1e-13ec-4136-9015-30fbe2563f82)


