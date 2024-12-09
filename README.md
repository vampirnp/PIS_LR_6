# PIS_LR_6

## 1. Выбор архитектуры
Для данной системы выбрал *микросервисную* архитектуру так как она наиболее подходящая. 
Этот выбор обоснован следующими причинами:

- Масштабируемость: *Микросервисная* архитектура позволяет легко масштабировать отдельные компоненты системы в зависимости от нагрузки. Например, сервис оплаты может быть масштабирован независимо от сервиса управления корзиной.
- Гибкость и адаптивность: Микросервисы могут быть разработаны, развернуты и обновлены независимо друг от друга, что упрощает внедрение новых функций и исправление ошибок.
- Интеграция со сторонними системами: Микросервисная архитектура упрощает интеграцию с внешними системами, такими как платежные шлюзы, системы управления складом.
- Отказоустойчивость: В случае сбоя одного из микросервисов, остальные части системы могут продолжать работать, что повышает общую надежность системы.


## 2. Основные компоненты
- Frontend: React 
- Backend Services: Spring Boot
- Database: PostgreSQL
- Внешний сервис: Payment Service (например, Sberpay или PayPal)

![image](https://github.com/user-attachments/assets/9af9515e-501c-42cd-a29e-50a8af04758c)

### 2.1. Компоненты системы
Система будет состоять из следующих микросервисов:

- User Service: Управление пользователями и их данными.
- Product Service: Управление товарами и их данными.
- Cart Service: Управление корзиной пользователя.
- Order Service: Управление заказами.
- Payment Service: Обработка платежей.
- Delivery Service: Управление доставкой.
- Notification Service: Уведомления пользователей.
- Интеграция со сторонней системой
- Для обработки платежей система будет интегрирована с платежным шлюзом, таким как Sberpay или PayPal. Взаимодействие с платежным шлюзом будет осуществляться через REST API.

![image](https://github.com/user-attachments/assets/0f3e97f6-bd3a-4048-aa8e-0bf312e5c8ae)


## 3. Взаимодействие между сервисами:
- Синхронное взаимодействие: Используютя для операций, требующих немедленного ответа, таких как добавление товара в корзину или создание заказа. Протокол: HTTP/REST.
- Асинхронное взаимодействие: Используютя для операций, которые могут выполняться в фоновом режиме, таких как уведомления пользователей или обработка платежей. Протокол: HTTP/REST/Kafka/TLS.
 
### Все Протоколы связи которые используются
- От сервиса к сервису: HTTP/REST
- Обработка платежей: HTTP/REST/Kafka/TLS.
- Работа с БД: JDBC

Айран топчик
