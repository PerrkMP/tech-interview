# Вопросы Middle Backend
---

### Стек
_ООП, SQL, Postgres, Redis/Memcached, RabbitMQ, FastAPI, Git & Git-flow, Docker, pytest, Celery, проектирования HTTP API,
GitLab CI/CD, Clean architecture, mypy, flake8_

### Блиц

1. Поток выполняется в отдельном адресном пространстве: один поток не может получить доступ к переменным и структурам данных другого. Верно ли утверждение? 
**Ответ:** Утверждение верно. В многопоточных программах каждый поток выполняется в отдельном адресном пространстве, что означает, что каждый поток имеет свои собственные переменные и структуры данных. При этом, каждый поток имеет доступ только к своим локальным переменным и может обмениваться данными с другими потоками только через явно определенные механизмы синхронизации, такие как блокировки или семафоры.
2. UDP — stateless, TCP — stateful. Верно ли утверждение? 
**Ответ:** Утверждение верно. UDP (User Datagram Protocol) является протоколом без установления соединения и не сохраняет состояние между отправителем и получателем. Каждое UDP-сообщение (датаграмма) рассматривается независимо и может быть отправлено или получено независимо от других датаграмм. В отличие от этого, TCP (Transmission Control Protocol) является протоколом с установлением соединения и сохраняет состояние между отправителем и получателем. TCP гарантирует доставку данных в правильном порядке и обеспечивает надежное соединение.
3. Какой метод шифрования используется для создание сессионного ключа в HTTPS? 
**Ответ:** В HTTPS для создания сессионного ключа (session key) используется метод шифрования, известный как асимметричное шифрование (asymmetric encryption). Обычно используется алгоритм RSA (Rivest-Shamir-Adleman) для генерации пары ключей: публичного и приватного. Публичный ключ используется для шифрования сессионного ключа на стороне сервера, а приватный ключ используется для его расшифровки на стороне клиента. Это обеспечивает конфиденциальность передачи сессионного ключа по открытому каналу.
4. Для чего используется оператор DISTINCT? 
**Ответ:** Оператор DISTINCT используется в языке SQL для удаления повторяющихся значений из результирующего набора данных. Он применяется в команде SELECT и позволяет выбрать уникальные значения из указанных столбцов. Таким образом, оператор DISTINCT позволяет получить только уникальные строки или значения в результирующем наборе, исключая повторения.
```sql
SELECT DISTINCT column
FROM table;
```
5. Назови дефолтный тип индекса в PostgreSQL
**Ответ:** В PostgreSQL дефолтным типом индекса является B-дерево (B-tree). B-дерево обеспечивает эффективный поиск и сортировку данных в базе данных. Оно поддерживает операции вставки, удаления и поиска со сложностью O(log n), где n - количество элементов в индексе. B-дерево является самым распространенным типом индекса в PostgreSQL и обеспечивает хорошую производительность для большинства типов запросов.
6. Назови 4 уровня изоляции транзакций в стандарте SQL? 
**Ответ:** В стандарте SQL (Structured Query Language) определены 4 уровня изоляции транзакций:
  - **READ UNCOMMITTED** (чтение неподтвержденных данных): разрешает чтение данных, которые еще не подтверждены другими транзакциями. Может привести к проблемам с неповторяемым чтением и фантомным чтением.
  - **READ COMMITTED** (чтение подтвержденных данных): разрешает чтение только подтвержденных данных. Предотвращает проблему неповторяемого чтения, но может привести к проблеме фантомного чтения.
  - **REPEATABLE READ** (повторяемое чтение): гарантирует, что одна и та же транзакция будет видеть одни и те же данные во время своего выполнения. Предотвращает неповторяемое чтение и фантомное чтение.
  - **SERIALIZABLE** (сериализуемость): обеспечивает полную изоляцию транзакций, гарантируя, что все транзакции выполняются последовательно, как будто они выполняются последовательно друг за другом. Предотвращает все проблемы неповторяемого чтения, фантомного чтения и неповторяемого записи.
7. Какова амортизированная сложность вставки элемента в конец массива? (под массивом имеется в виду list для Python) 
**Ответ:** Амортизированная сложность вставки элемента в конец массива (списка) в языке Python (используя list) - O(1). В среднем, вставка элемента в конец массива требует константного времени, независимо от размера массива. Это связано с тем, что Python использует динамическое увеличение размера массива при необходимости, что позволяет избежать копирования всех элементов при каждой вставке.
8. Открытый вопрос. Каким критериям должен соответствовать хороший код по твоему мнению? ~5 пунктов в приоритете важности
**Ответ:** Хороший код соответствует определенным критериям, которые могут варьироваться в зависимости от контекста и требований проекта. Однако, вот некоторые общие критерии, которым должен соответствовать хороший код:
  - **Читаемость**: Хороший код должен быть легко читаемым и понятным для других разработчиков. Он должен иметь понятные имена переменных, функций и классов, хорошую структуру и форматирование, а также комментарии там, где это необходимо.
  - **Модульность**: Хороший код должен быть разделен на небольшие, логические модули, которые решают конкретные задачи. Это делает код более организованным, легко поддерживаемым и повторно используемым.
  - **Эффективность**: Хороший код должен быть эффективным и оптимизированным. Он должен выполнять свою задачу с минимальным использованием ресурсов, таких как память и процессорное время.
  - **Безопасность**: Хороший код должен быть безопасным и защищенным от уязвимостей. Он должен обрабатывать ошибки и исключительные ситуации, проверять входные данные на корректность и предотвращать возможные атаки.
  - **Тестируемость**: Хороший код должен быть легко тестируемым. Он должен иметь модульные тесты, которые проверяют его функциональность и устойчивость к изменениям.

### По стеку

#### ООП (Объектно-ориентированное программирование):

Вопрос 1: Что такое объектно-ориентированное программирование?

Вопрос 2: Какие основные принципы лежат в основе ООП?

Вопрос 3: Чем отличается класс от объекта?

Вопрос 4: Что такое наследование и полиморфизм в контексте ООП?

Вопрос 5: Какие преимущества предоставляет ООП в разработке программного обеспечения?

**Ответы:**

Объектно-ориентированное программирование (ООП) - это парадигма программирования, которая организует программу вокруг объектов, которые представляют сущности реального мира и взаимодействуют друг с другом.

Основные принципы ООП включают инкапсуляцию, наследование, полиморфизм и абстракцию.

Класс - это шаблон или определение, которое описывает свойства и методы объекта. Объект - это экземпляр класса, который может иметь свои уникальные значения свойств.

Наследование позволяет создавать новые классы на основе существующих, наследуя их свойства и методы. Полиморфизм позволяет использовать один и тот же интерфейс для работы с разными типами объектов.

ООП предоставляет преимущества, такие как повторное использование кода, легкость сопровождения, модульность, увеличение производительности разработки и понятность кода.

#### SQL и БД (PostgreSQL):

Вопрос 1: Что такое SQL и какие типы запросов поддерживает?

Вопрос 2: Что такое реляционная база данных?

Вопрос 3: Какие операции можно выполнять с использованием SQL?

Вопрос 4: Что такое индексы в базе данных и как их использовать?

Вопрос 5: Что такое транзакции в контексте базы данных?

**Ответы:**

SQL (Structured Query Language) - язык программирования для работы с реляционными базами данных. Он поддерживает типы запросов, такие как SELECT (запрос данных), INSERT (вставка данных), UPDATE (обновление данных), DELETE (удаление данных) и другие.

Реляционная база данных - это коллекция таблиц, которые хранят данные в виде реляционных структур, состоящих из строк и столбцов.

С использованием SQL можно выполнять операции выборки данных (SELECT), вставки данных (INSERT), обновления данных (UPDATE), удаления данных (DELETE), создания таблиц (CREATE TABLE), изменения таблиц (ALTER TABLE) и другие операции, связанные с управлением данными.

Индексы в базе данных используются для ускорения поиска и сортировки данных. Они создаются на определенных столбцах таблицы и позволяют быстро находить нужные данные по заданным условиям.

Транзакции - это логические единицы работы с базой данных, которые обеспечивают целостность и непрерывность операций. Транзакции позволяют группировать несколько операций в одну логическую единицу, обеспечивая атомарность, согласованность, изолированность и долговечность данных (ACID-свойства).

#### Redis/Memcached:

Вопрос 1: Что такое Redis и Memcached?

Вопрос 2: В чем разница между Redis и Memcached?

Вопрос 3: Какие возможности предоставляют Redis и Memcached?

Вопрос 4: Какие типы данных поддерживаются в Redis и Memcached?

Вопрос 5: Какие сценарии использования подходят для Redis и Memcached?

**Ответы:**

Redis и Memcached - это два популярных инструмента для кэширования данных в памяти.

Основная разница между Redis и Memcached заключается в их функциональности и возможностях. Redis предоставляет более широкий спектр возможностей, таких как хранение различных типов данных, поддержка публикации/подписки, управление списками, наборами и множествами данных, а также сохранение данных на диск. Memcached является более простым и легковесным инструментом, ориентированным на кэширование данных.

Redis и Memcached предоставляют возможности кэширования данных в оперативной памяти, что позволяет значительно ускорить доступ к данным. Они обеспечивают быстрый доступ к данным благодаря использованию хэш-таблицы и поддержке параллельного доступа.

Redis поддерживает различные типы данных, такие как строки, списки, наборы, хэши и упорядоченные множества. Memcached поддерживает только строки.

Redis и Memcached подходят для сценариев, где требуется быстрый доступ к часто запрашиваемым данным, кэширование запросов к базе данных, распределенные системы, сессионное хранение и другие задачи, связанные с повышением производительности приложений.

#### RabbitMQ:

Вопрос 1: Что такое RabbitMQ и в чем заключается его роль?

Вопрос 2: Какие понятия и компоненты связаны с RabbitMQ?

Вопрос 3: Как RabbitMQ обеспечивает асинхронное взаимодействие между приложениями?

Вопрос 4: Какие протоколы и паттерны взаимодействия поддерживает RabbitMQ?

Вопрос 5: Какие преимущества предоставляет RabbitMQ?

**Ответы:**

RabbitMQ - это сообществом разработанный брокер сообщений, который обеспечивает асинхронную коммуникацию между различными компонентами приложения.

В RabbitMQ существуют понятия сообщений (messages), очередей (queues), обменников (exchanges) и связей (bindings). Сообщения передаются из одной точки в другую через обменники и маршрутизируются на основе определенных правил, заданных через связи.

RabbitMQ позволяет приложениям обмениваться сообщениями асинхронно, отправлять сообщения в очередь и получать их из очереди в удобное время. Это обеспечивает отделение процессов и позволяет строить гибкие, масштабируемые системы.

RabbitMQ поддерживает протоколы AMQP (Advanced Message Queuing Protocol), MQTT (Message Queuing Telemetry Transport) и другие. Он также поддерживает различные паттерны взаимодействия, такие как point-to-point, publish/subscribe и др.

RabbitMQ предоставляет надежную и гибкую систему обмена сообщениями, что обеспечивает устойчивость и масштабируемость приложений. Он также позволяет создавать сложные сообщества и распределенные системы, где различные компоненты могут взаимодействовать между собой асинхронно.

#### FastAPI:

Вопрос 1: Что такое FastAPI и в чем его особенности?

Вопрос 2: Какие преимущества предоставляет FastAPI по сравнению с другими фреймворками для разработки веб-приложений?

Вопрос 3: Какие функциональные возможности предоставляет FastAPI для создания API?

Вопрос 4: Как FastAPI обрабатывает запросы и возвращает ответы?

Вопрос 5: Какие инструменты и технологии используются в экосистеме FastAPI?

**Ответы:**

FastAPI - это современный, быстрый (отсюда название) и мощный фреймворк для разработки веб-приложений и API с использованием языка Python. Он основан на типизации данных (с помощью Python 3.7+ и аннотаций типов) и асинхронном программировании (с помощью asyncio).

FastAPI предоставляет высокую производительность за счет использования компилятора Python (Pydantic), асинхронности и автоматической генерации документации на основе аннотаций типов.

FastAPI позволяет создавать мощные API с поддержкой валидации данных, автоматической документации, автоматической генерации схемы данных (OpenAPI и JSON Schema) и многое другое. Он также поддерживает обработку запросов с использованием путей, параметров, тела запроса, пагинацию, авторизацию и другие функциональности.

FastAPI использует асинхронное программирование и обрабатывает запросы и ответы с использованием синтаксиса async/await. Он обеспечивает высокую производительность благодаря использованию компилятора Pydantic для валидации и сериализации данных.

В экосистеме FastAPI используются такие инструменты и технологии, как Pydantic (для работы с типизацией данных), SQLAlchemy (для работы с базами данных), JWT (JSON Web Tokens) для авторизации, Docker (для контейнеризации) и другие, что делает его гибким и удобным инструментом для разработки веб-приложений и API.

> Далее для справки

**OpenAPI:**
OpenAPI (ранее известный как Swagger) - это набор спецификаций и инструментов, которые позволяют описывать и визуализировать API в машиночитаемом формате. Он определяет стандарты и соглашения для документирования и описания функциональности, структуры данных, путей, методов и параметров, поддерживаемых API. Файлы OpenAPI обычно представлены в формате YAML или JSON и содержат информацию о ресурсах API, авторизации, параметрах запросов и ответах. Они могут быть использованы для автоматической генерации документации, создания клиентских библиотек и выполнения других операций, связанных с разработкой и использованием API.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/items/{item_id}")
async def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}
```

В этом примере FastAPI используется для создания простого API, где определен единственный эндпоинт `/items/{item_id}`. Здесь мы передаем параметры `item_id` и `q` в запросе, и FastAPI автоматически генерирует документацию на основе аннотаций типов и аргументов функции.

**JSON Schema:**
JSON Schema - это язык описания структуры и формата данных в формате JSON. Он определяет правила и ограничения для валидации и валидации JSON-данных. JSON Schema позволяет задавать требования к типам данных, значениям, обязательным и необязательным полям, ограничениям на числовые значения, паттерным для строк и другие правила валидации. JSON Schema может быть использован для проверки корректности JSON-данных и установления соответствия данным определенной схеме. Он может быть также использован для генерации документации и автоматической валидации данных, используемых в API.

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class Item(BaseModel):
    name: str
    price: float

@app.post("/items/")
async def create_item(item: Item):
    return item
```

В этом примере мы определяем модель Item, которая описывает структуру данных объекта item. С помощью JSON Schema, встроенного в Pydantic (используемого FastAPI), мы можем автоматически валидировать данные, передаваемые в теле запроса при создании элемента (/items/). Если данные не соответствуют схеме, будет возвращена ошибка.

`@app.post("/items/", response_model=Item)` - для совместного использования.

#### Git и Git-flow:

**Вопросы:**

Что такое Git, и зачем он используется в разработке программного обеспечения?

Как создать новую ветку в Git?

Какие команды используются для слияния веток в Git?

Что такое коммит в Git?

Как откатиться к предыдущей версии кода в Git?

**Ответы:**

Git - это распределенная система контроля версий, которая позволяет разработчикам отслеживать изменения в коде, работать в команде и управлять историей проекта. Он используется для управления кодом, обеспечения совместной работы над проектом, отслеживания изменений, восстановления предыдущих версий кода и слияния внесенных изменений.

Для создания новой ветки в Git используется команда "git branch" с указанием имени новой ветки. Например, "git branch new-feature".

Для слияния веток в Git используется команда "git merge" с указанием ветки, которую необходимо слить с текущей. Например, "git merge feature-branch".

Коммит в Git - это фиксация изменений в коде. Каждый коммит содержит набор изменений и комментарий, описывающий внесенные изменения. Коммиты позволяют отслеживать историю изменений и возвращаться к предыдущим версиям кода.

Для отката к предыдущей версии кода в Git используется команда "git checkout" с указанием идентификатора коммита или имени ветки. Например, "git checkout HEAD~1" откатит код на один коммит назад.

#### Docker:

**Вопросы:**

Что такое Docker, и какие преимущества он предоставляет в разработке приложений?

Как создать Docker-контейнер для своего приложения?

Какие команды Docker используются для управления контейнерами?

Что такое Dockerfile, и зачем он нужен?

Как обеспечить взаимодействие между контейнерами Docker?

**Ответы:**

Docker - это платформа, которая позволяет упаковывать приложения и их зависимости в контейнеры для облегчения развертывания и масштабирования. Он предоставляет изолированное окружение для приложения, что позволяет запускать его на разных хост-системах без проблем совместимости и конфликтов зависимостей. Docker также обеспечивает удобную среду для разработки, тестирования и развертывания приложений.

Для создания Docker-контейнера для своего приложения необходимо создать Dockerfile, который содержит инструкции для сборки контейнера. Затем используется команда "docker build" для сборки контейнера на основе Dockerfile.

Команды Docker, используемые для управления контейнерами, включают:

"docker run" - запуск контейнера из образа.

"docker stop" - остановка контейнера.

"docker start" - запуск остановленного контейнера.

"docker restart" - перезапуск контейнера.

"docker rm" - удаление контейнера.

Dockerfile - это текстовый файл, который содержит инструкции для сборки Docker-образа. Он определяет окружение и зависимости, необходимые для запуска приложения в контейнере. Dockerfile описывает шаги по установке пакетов, настройке среды выполнения и копированию файлов в контейнер.

Взаимодействие между контейнерами Docker может быть обеспечено с помощью сетевых подключений Docker. Контейнеры могут быть связаны в одну сеть, и они смогут взаимодействовать друг с другом по сети с использованием имен контейнеров или IP-адресов. Docker также предоставляет возможность настройки портов для доступа к сервисам внутри контейнера извне.

#### pytest:

**Вопросы:**

Что такое pytest, и как он отличается от стандартного модуля unittest в Python?

Как запустить тесты с использованием pytest?

Какие основные функции и возможности предоставляет pytest для написания тестов?

Какие механизмы в pytest используются для организации и структурирования тестов?

Какие типы тестов можно написать с помощью pytest?

**Ответы:**

pytest - это фреймворк для написания автоматических тестов на языке Python. Он отличается от стандартного модуля unittest более простым и понятным синтаксисом, автоматическим обнаружением и запуском тестов, а также широким набором возможностей для удобного тестирования.

Для запуска тестов с использованием pytest необходимо выполнить команду pytest в директории с тестовыми файлами. Pytest автоматически обнаружит и запустит все тестовые функции и классы в файлах, и отобразит результаты выполнения тестов.

pytest предоставляет множество функций и возможностей для написания тестов, включая:

assert выражения для проверки условий.
Фикстуры (fixtures) для подготовки и предоставления тестовым функциям необходимых ресурсов и данных.
Параметризация тестов для выполнения одного и того же теста с разными наборами входных данных.
Маркировка тестов для их категоризации и запуска по определенным правилам.
Механизмы для обработки ошибок и исключений в тестах.
Для организации и структурирования тестов в pytest используются:

Файлы и директории с определенным префиксом (например, test_) для автоматического обнаружения тестов.
Модули и пакеты для группировки связанных тестов.
Маркировки тестов для их классификации и фильтрации.
С помощью pytest можно написать различные типы тестов, включая:

Модульные тесты для проверки отдельных компонентов или модулей кода.
Интеграционные тесты для проверки взаимодействия между различными компонентами системы.
Тесты симуляции и мокирования для проверки поведения кода в контролируемой среде.
Функциональные тесты для проверки работы приложения в целом.

**Celery:**

**Вопросы:**

Что такое Celery, и какую проблему он решает в разработке приложений?

Как создать и определить задачу в Celery?

Как запустить и выполнить задачу с использованием Celery?

Какие компоненты входят в архитектуру Celery и как они взаимодействуют между собой?

Как обеспечить масштабируемость и отказоустойчивость в Celery?

**Ответы:**

Celery - это распределенная система обработки задач, которая позволяет асинхронно выполнять фоновые задачи в приложении. Он решает проблему выполнения долгих операций, которые не должны блокировать основной поток выполнения приложения. Celery позволяет разделить задачи на независимые единицы работы и выполнять их асинхронно в фоновом режиме.

Для создания и определения задачи в Celery необходимо определить функцию, которая будет выполнять задачу, и пометить ее декоратором @task. Внутри функции определяется логика задачи, аргументы и результаты.

Для запуска и выполнения задачи с использованием Celery необходимо отправить задачу в очередь (queue). Это делается с помощью вызова функции-задачи с передачей необходимых аргументов. Затем Celery автоматически обрабатывает задачи, выполняя их в отдельных рабочих процессах или на удаленных узлах.

В архитектуру Celery входят следующие компоненты:

- Задачи (Tasks): Функции, которые выполняют определенную задачу.
- Брокер сообщений (Message Broker): Компонент, который обеспечивает связь между отправителем задач и исполнителями.
- Рабочие процессы (Workers): Процессы, которые получают задачи из очереди и выполняют их.
- Результаты (Results): Механизм, который позволяет отслеживать и получать результаты выполнения задач.
Мониторы и инструменты управления: Инструменты для мониторинга и управления Celery-кластером.

Для обеспечения масштабируемости и отказоустойчивости в Celery можно использовать следующие подходы:

- Горизонтальное масштабирование путем запуска дополнительных рабочих процессов на разных узлах.
- Распределенный брокер сообщений для обеспечения надежной доставки задач.
- Конфигурирование поведения и параметров Celery для оптимальной производительности и надежности.
- Мониторинг и резервное копирование системы Celery для предотвращения потери задач и результатов и обеспечения непрерывной работы.

#### Проектирование HTTP API не на Django:

**Вопросы:**

Что такое HTTP API и почему он важен в разработке современных веб-приложений?

Какие архитектурные стили и подходы могут быть использованы при проектировании HTTP API?

Какие фреймворки и инструменты могут быть использованы для создания HTTP API не на Django?

Какие основные принципы RESTful архитектуры следует учитывать при проектировании HTTP API?

Какие методы HTTP запросов можно использовать в HTTP API и в каких ситуациях?

**Ответы:**

HTTP API - это интерфейс приложения, который позволяет клиентам обмениваться данными и взаимодействовать с веб-приложением по протоколу HTTP. HTTP API важен в разработке современных веб-приложений, так как позволяет расширять и масштабировать приложения, упрощает интеграцию с другими системами и обеспечивает гибкость взаимодействия с клиентами.

При проектировании HTTP API можно использовать различные архитектурные стили и подходы, такие как RESTful, GraphQL, RPC (Remote Procedure Call) и т. д. Каждый стиль имеет свои преимущества и особенности, и выбор зависит от требований и целей проекта.

Для создания HTTP API не на Django можно использовать различные фреймворки и инструменты, например:

- Flask: Легкий фреймворк для создания веб-приложений на языке Python.
- FastAPI: Современный фреймворк для создания веб-приложений на языке Python с поддержкой асинхронности.
- Express.js: Фреймворк для создания веб-приложений на языке JavaScript (Node.js).
- ASP.NET Core: Фреймворк для создания веб-приложений на языке C#.

При проектировании HTTP API с использованием принципов RESTful архитектуры следует учитывать:

- Использование корректных методов HTTP (GET, POST, PUT, DELETE) для операций чтения, создания, обновления и удаления данных.
- Использование понятных и описательных URL-адресов (эндпоинтов) для идентификации ресурсов.
- Работа с представлением данных (например, JSON) и поддержка формата ответа по умолчанию.
- Управление состоянием сессии на стороне клиента или использование авторизации и токенов доступа.

В HTTP API можно использовать различные методы HTTP запросов, такие как:

- GET: Запрос на получение данных.
- POST: Запрос на создание новых данных.
- PUT: Запрос на обновление существующих данных.
- DELETE: Запрос на удаление данных.
- PATCH: Запрос на частичное обновление данных.

#### SQL запросы без ORM:

**Вопросы:**

Что такое SQL, и какие операции и функции он предоставляет для работы с базами данных?

Что такое подзапрос (subquery) в SQL и как оно может быть использовано в запросах без ORM?

Как выполнить соединение (JOIN) двух таблиц без использования ORM?

Как выполнить условную сортировку (ORDER BY) в SQL запросе без ORM?

Как выполнить группировку (GROUP BY) и применить агрегатные функции без использования ORM?

**Ответы:**

SQL (Structured Query Language) - это язык программирования, используемый для работы с реляционными базами данных. Он предоставляет операции и функции для создания, изменения и извлечения данных из базы данных. Операции SQL включают SELECT (выборка данных), INSERT (добавление данных), UPDATE (обновление данных) и DELETE (удаление данных), а также операции для создания таблиц, индексов и других структур данных.

Подзапрос в SQL представляет собой запрос, вложенный в другой запрос. Он может использоваться для извлечения данных из внутреннего запроса и использования их во внешнем запросе. Например, подзапрос может использоваться для фильтрации результатов, выполнения агрегатных функций или связывания данных из разных таблиц.

Для выполнения соединения двух таблиц без ORM можно использовать операторы JOIN и ON в SQL. Например, чтобы выполнить внутреннее соединение, вы можете написать следующий запрос:
```sql
SELECT *
FROM table1
JOIN table2 ON table1.column = table2.column;
```

Для выполнения условной сортировки в SQL можно использовать оператор CASE. Например, чтобы сортировать результаты по столбцу "name" в порядке возрастания, а затем в порядке убывания, можно написать следующий запрос:
```sql
SELECT *
FROM table
ORDER BY CASE
    WHEN name = 'John' THEN 1
    WHEN name = 'Alice' THEN 2
    ELSE 3
END;
```

> Условная сортировка (Conditional Sorting) - это процесс сортировки данных в результате запроса с учетом определенных условий или критериев. Вместо простой сортировки по одному или нескольким столбцам, условная сортировка позволяет определить специфические правила сортировки в зависимости от значений или условий.

Для выполнения группировки и применения агрегатных функций в SQL можно использовать ключевое слово GROUP BY. Например, чтобы найти сумму значений столбца "amount" для каждой уникальной категории в таблице, можно написать следующий запрос:
```sql
SELECT category, SUM(amount)
FROM table
GROUP BY category;
```

#### GitLab CI/CD:

GitLab CI/CD - это система непрерывной интеграции и доставки (Continuous Integration/Continuous Delivery), предоставляемая платформой GitLab. Она позволяет автоматизировать процессы сборки, тестирования, развертывания и доставки приложений на основе репозитория GitLab.

**Вопросы:**

Что такое непрерывная интеграция (CI) и непрерывная доставка (CD) в контексте разработки программного обеспечения?

Какие компоненты входят в систему GitLab CI/CD?

Как создать и настроить пайплайн CI/CD в GitLab?

Какие типы задач можно выполнять в пайплайнах GitLab CI/CD?

Как обеспечить безопасность и надежность процесса CI/CD в GitLab?

**Ответы:**

Непрерывная интеграция (CI) и непрерывная доставка (CD) - это подходы к разработке программного обеспечения, которые предполагают автоматизацию процессов сборки, тестирования и доставки приложений. CI обеспечивает регулярное и автоматическое интегрирование изменений в общую кодовую базу, а CD обеспечивает автоматическую и повторяемую доставку приложения в производственную среду.

В систему GitLab CI/CD входят следующие компоненты:

- Репозиторий GitLab: Хранит код приложения и конфигурацию пайплайнов CI/CD.
- Runner: Процесс или виртуальная машина, которая выполняет задачи в пайплайнах.
- Конфигурационный файл .gitlab-ci.yml: Определяет структуру и настройки пайплайна CI/CD.
- Для создания и настройки пайплайна CI/CD в GitLab необходимо:

Создать файл .gitlab-ci.yml в корневом каталоге репозитория.
Определить структуру пайплайна, включая этапы (stages) и задачи (jobs).
Настроить параметры задач, такие как среда выполнения, скрипты, переменные окружения и т. д.

В пайплайнах GitLab CI/CD можно выполнять различные типы задач, включая:

- Сборка приложения: Компиляция и сборка кода приложения.
- Тестирование: Запуск автоматических тестов для проверки работоспособности приложения.
- Деплоймент: Развертывание приложения в целевой среде, например, на сервере или в облаке.
- Проверка безопасности: Выполнение сканирования уязвимостей или анализа кода на предмет потенциальных уязвимостей.

Для обеспечения безопасности и надежности процесса CI/CD в GitLab можно использовать следующие подходы:

- Использование контейнеров для изоляции и управления окружением выполнения задач.
- Настройка автоматического тестирования и проверок качества кода для обнаружения потенциальных проблем.
- Управление доступом и разграничением прав доступа к репозиторию и пайплайнам.
- Регулярное резервное копирование конфигурации и данных пайплайнов.
- Мониторинг и логирование процесса CI/CD для быстрого обнаружения и устранения проблем.

#### Clean architecture, паттерны проектирования:

> Паттерны проектирования - это повторяемые решения для типичных проблем в разработке программного обеспечения. Они представляют собой проверенные подходы к проектированию систем, которые способствуют улучшению структуры, расширяемости, поддерживаемости и повторного использования кода.

**Вопросы:**

Что такое Clean architecture, и какие основные принципы она предлагает для разработки программного обеспечения?

Какие основные компоненты включает Clean architecture, и как они взаимодействуют между собой?

Какие преимущества Clean architecture приносит в разработке программного обеспечения?

Какие паттерны проектирования часто используются в контексте Clean architecture?

Как можно применить Clean architecture и паттерны проектирования для улучшения существующего проекта?

**Ответы:**

Clean architecture - это подход к проектированию программного обеспечения, который ставит акцент на разделение системы на слои и явное определение зависимостей между ними. Основные принципы Clean architecture включают разделение бизнес-логики от деталей реализации, инверсию зависимостей, поддержку тестирования и независимость от фреймворков или внешних ресурсов.

Clean architecture включает следующие компоненты:

- Entities (Сущности): Представляют бизнес-модели и правила бизнес-логики.
- Use Cases (Использование): Содержат специфическую для приложения бизнес-логику.
- Interface Adapters (Адаптеры интерфейса): Переводят данные между слоями и обрабатывают взаимодействие с внешними системами.
- Frameworks & Drivers (Фреймворки и драйверы): Содержат детали реализации и взаимодействия с фреймворками и внешними ресурсами.

Преимущества Clean architecture включают:

- Легкость тестирования: Чистая архитектура обеспечивает высокую тестируемость компонентов, что упрощает разработку автоматических тестов.
- Гибкость и расширяемость: Чистая архитектура разделяет компоненты и устанавливает явные зависимости, что позволяет легко заменять или добавлять новые компоненты без влияния на остальную систему.
- Независимость от фреймворков: Чистая архитектура позволяет разрабатывать систему, не привязываясь к конкретным фреймворкам или внешним ресурсам, что облегчает поддержку и миграцию.

Некоторые паттерны проектирования, часто используемые в контексте Clean architecture, включают:

- Dependency Injection (Внедрение зависимостей): Паттерн, позволяющий управлять зависимостями компонентов и обеспечивающий инверсию зависимостей.
- Repository Pattern (Паттерн репозитория): Паттерн, который абстрагирует доступ к данным и обеспечивает единый интерфейс для работы с хранилищем данных.
- Observer Pattern (Паттерн наблюдателя): Паттерн, который позволяет объектам подписываться и получать уведомления об изменениях состояния других объектов.

Для улучшения существующего проекта с помощью Clean architecture и паттернов проектирования можно:

- Выделить ядро бизнес-логики и вынести его в отдельный слой.
- Использовать Dependency Injection для управления зависимостями и обеспечения инверсии зависимостей.
- Применить паттерны проектирования для реализации отдельных компонентов, таких как репозитории, сервисы и контроллеры.
- Разделить пользовательский интерфейс от бизнес-логики, чтобы обеспечить лучшую модульность и тестируемость кода.
- Обновить структуру проекта, чтобы отразить слои Clean architecture и сделать код более понятным и поддерживаемым.

#### Mypy:
Mypy - это инструмент статической типизации для языка программирования Python. Он позволяет разработчикам проверять типы переменных, функций и модулей на этапе разработки, что помогает обнаруживать потенциальные ошибки и улучшает читаемость и надежность кода. Mypy работает на основе аннотаций типов, которые добавляются к коду в виде специальных комментариев или встроенных строк документации.

Типизация по наступлению - это подход, который позволяет использовать как динамическую, так и статическую типизацию в одном языке программирования. В Python это означает, что можно использовать аннотации типов в некоторых частях кода и оставить другие части кода без аннотаций. Mypy позволяет постепенно внедрять статическую типизацию в существующий проект.

`mypy mymodule.py`

#### Flake8:
Flake8 - это инструмент статического анализа кода для языка программирования Python. Он проверяет код на соответствие стандартам оформления и рекомендациям PEP 8, а также на наличие потенциальных проблем и ошибок в коде. Flake8 объединяет несколько инструментов, включая PyFlakes, pycodestyle и McCabe, для выполнения проверок стиля кодирования, обнаружения неиспользуемого кода и анализа сложности кода.

`flake8 mymodule.py`
