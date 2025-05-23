# **Практическая работа №3**

## 1. **CI**
   
   Было настроено CI включающее pylint и запуск интеграционных тестов.
   yml файл:
   
   https://github.com/MASHAGOLOVANOVA/mvp-2-spms/blob/dss-practice3/main/.github/workflows/main.yml
 

## 2. **Масштабирование компонентов**
  
   Для масштабирования приложения было выбрано балансировщик нагрузки L7 с репликацией компонента через Docker Compose. 
   Преимущества способа масшитабирования:
   1. Управление трафиком: L7 балансировщик может направлять запросы на основе их содержимого (например, URL), что позволяет лучше распределять нагрузку.
   2. Легкость масштабирования: Можно легко добавлять или удалять копии сервисов в зависимости от нагрузки, что помогает справляться с увеличением трафика.
   3. Изоляция приложений: Docker изолирует приложения в контейнерах, что упрощает управление их зависимостями и версиями.
   4. Простота развертывания: Docker Compose позволяет описывать все сервисы в одном файле, что упрощает их запуск и управление.
   5. Высокая доступность: Если один экземпляр сервиса не работает, трафик автоматически перенаправляется на другие работающие экземпляры.

   Балансировщик реализован с помощью Nginx:
   1. Поддержка используемых в приложении протоколов.
   2. Легкая конфигурация.
   3. Высокая производительность засчет ассинхронной архитектуры.
   4. Хорошая документация и большое сообщество.

   Обновленный докер-компоуз: 
   
   https://github.com/MASHAGOLOVANOVA/mvp-2-spms/blob/dss-practice3/main/docker-compose.yml

![image](https://github.com/user-attachments/assets/be6285fe-33ed-4ca8-bb8a-14d398df2e6a)
   

## 3. **GrayLog**
