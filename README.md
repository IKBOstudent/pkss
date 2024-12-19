# Документирование приложения турфирмы

## 1. Структура функциональных возможностей (Mind Map)

```mermaid
mindmap
  root((Турфирма))
    Пользователи
      Регистрация
      Аутентификация
      Профиль
    Поиск
      Алгоритмы поиска туров
      Списки подходящих туров
    Бронирование
      Создание заказа
      Подтверждение заказа
      Оплата заказа
    Эффективность
      Сбор активности пользователя
      Анализ предпочтений клиентов
      Генерация аналитических данных
    Коммуникации
      Уведомления
      Обратная связь
    Оплата
      Оплата заказа
      История транзакций
    Безопасность
      Аутентификация
      Защита данных
      Модерация контента
    Интеграции
      Сторонние платежные системы
```

### Описание:

Эта диаграмма иллюстрирует структуру функциональных возможностей приложения.

## Основные узлы и их значение:

* <u>Пользователи</u> функционал авторизации и управления аккаунтом

* <u>Защита данных</u> безопасность приложения.

* <u>Поиск</u> процессы поиска туров по выбранным параметрам

* <u>Бронирование</u> процессы бронирования и оплаты туров





## 2. Диаграмма путешествия пользователя (User Journey Diagram)
```mermaid
journey
    title Путешествие пользователя приложения турфирмы
    section Регистрация
      Пользователь открывает приложение: 5: Пользователь
      Пользователь заполняет форму регистрации: 4: Пользователь
    section Поиск туров
      Пользователь открывает страницу поиска: 4: Пользователь
      Пользователь выбирает параметры поиска: 4: Пользователь
    section Выбор тура
      Пользователь выбирает тур: 5: Пользователь
    section Оформление заказа
      Пользователь открывает страницу заказа: 5: Пользователь
      Пользователь заполлняет форму: 5: Пользователь
      Пользователь подтверждает бронирование: 4: Пользователь
    section Оплата
      Пользователь открывает страницу оплаты: 4: Пользователь
      Пользователь вводит данные платежа: 5: Пользователь
      Пользователь подтверждает платеж: 5: Пользователь
    section Завершение
      Пользователь закрывает приложение: 5: Пользователь
```
### Описание:

Диаграмма описывает ключевые этапы взаимодействия пользователя с системой:

* Регистрация: пользователь вводит данные и проходит аунтефикацию

* Поиск туров: пользователь выбирает параметры поиска

* Выбор тура: переход на страницу тура

* Оформление заказа: создание заказа на конкретный тур

* Оплата: оплата брони тура

## 3. Квадрант-граф (Prioritization Quadrant)

```mermaid
quadrantChart

    title Приоритеты разработки функциональности

    x-axis Easy --> Hard

    y-axis Low Priority --> High Priority

    "Авторизация": [0.8, 0.8]

    "Поиск туров": [0.4, 0.75]

    "Создание заказов": [0.6, 0.85]

    "Оплата заказа": [0.6, 0.9]

    "Обратная связь": [0.6, 0.2]

    "Модерация контента": [0.4, 0.8]

    "Защита данных": [0.8, 0.7]

    "Оптимизации поисковых систем": [0.3, 0.3]
```
Квадрант-граф помогает приоритизировать разработку функций системы. Каждая точка соответствует функционалу:

* Ось X: сложность реализации (от простого к сложному).

* Ось Y: приоритет для пользователей (от низкого к высокому).


# 4. Гит граф (Gitgraph)

```mermaid
gitGraph
    commit id: "v0.1.0: Project initialization"
    commit id: "v0.2.0: Basic user interface"
    commit id: "v0.3.0: User registration feature"
    
    branch feature-auth
    checkout feature-auth
    commit id: "Add registration and authentication"
    commit id: "Implement auth service"
    checkout main
    merge feature-auth id: "Merge auth into main"
    commit id: "v0.4.0: Auth features release"

    branch feature-search
    checkout feature-search
    commit id: "Add search tours feature"
    commit id: "Implement search service"
    checkout main
    merge feature-search id: "Merge search into main"
    commit id: "v0.5.0: Search features release"

    branch feature-order
    checkout feature-order
    commit id: "Add creating and maintaining orders feature"
    commit id: "Implement order service"
    checkout main
    merge feature-order id: "Merge order into main"
    commit id: "v0.6.0: Order features release"
    
    branch feature-payments
    checkout feature-payments
    commit id: "Add payment processing"
    commit id: "Implement transaction history"
    checkout main
    merge feature-payments id: "Merge payment features into main"
    commit id: "v0.7.0: Payment processing release"
    
    branch feature-security
    checkout feature-security
    commit id: "Enhance user authentication"
    commit id: "Implement data protection measures"
    commit id: "Add content moderation features"
    checkout main
    merge feature-security id: "Merge security features into main"
    commit id: "v0.8.0: Security enhancements"
    
    commit id: "v1.0.0: First stable release"

```

### Описание:

 Гит-граф показывает процесс разработки системы через версии:

1. Основная ветка (main): стабильные версии системы.

2. Функциональные ветки: каждая ветка посвящена отдельной функциональности.

3. Слияния: после завершения работы над веткой, изменения интегрируются в main.
