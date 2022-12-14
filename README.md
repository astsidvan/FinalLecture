
**План тестирование возможности записаться на обучение профессии «Тестировщик ПО» на веб-сайт Нетологии.**

 ### 1.Перечень автоматизируемых сценариев

Перейдя на страницу https://netology.ru/programs/qa, записаться на обучение можно тремя способами:

1 способ. В начале страницы слева зеленая кнопка "Записаться" пролистывает вниз до формы «Запишитесь или получите консультацию».

2 способ. Начать пролистывать вниз и сверху (рядом с кнопкой "Войти") появится окно "Записаться" при нажатие пролистывает вниз до формы «Запишитесь или получите консультацию».

3 способ. Пролистать всю страницу вниз до формы «Запишитесь или получите консультацию».

-API тестирование

-Позитивные проверки

-Проверка поддержки MySQL 

-Проверка корректности данных записанных в БД

-UI тестирование

**Позитивное тестирование:**
1.	Ввести валидное имя на кириллице в поле Имя например “Иван”
2.	Ввести валидный номер телефона из 11 цифр “79999999999”
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об успешной отправки заявки._

**Негативное тестирование 1.:**
1.	Ввести не валидное значение (спецсимволы) в поле Имя “$%#%$^%”
2.	Ввести валидный номер телефона из 11 цифр “79999999999”
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об ошибке, поле Имя не может содержать спец символы._

**Негативное тестирование 2.:**
1.	Ввести не валидное имя на латинице в поле Имя “Ivan”
2.	Ввести валидный номер телефона из 11 цифр “79999999999”
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об ошибке, поле Имя заполнено некорректно._

**Негативное тестирование 3.:**
1.	Ввести не валидное имя, состоящее из 1 буквы на кириллице “И”
2.	Ввести валидный номер телефона из 11 цифр “79999999999”
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об ошибке, поле Имя Должно быть не короче 2 Символов._

**Негативное тестирование 4.:**
1.	Оставить поле Имя пустым
2.	Оставить поле Телефон пустым
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об ошибке, обязательное поле._

**Негативное тестирование 5.:**
1.	Ввести не валидное Имя, состоящее из цифр “43425342”
2.	Ввести валидный номер телефона из 11 цифр “79999999999”
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об ошибке, поле Имя заполнено некорректно._

**Негативное тестирование 6.:**
1.	Ввести не валидное имя, состоящее из 64 букв на латинице
2.	Ввести валидный номер телефона из 11 цифр “79999999999”
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об ошибке, слишком длинное поле._

**Негативное тестирование 7.:**
1.	Ввести валидное имя на кириллице в поле Имя “Иван”
2.	Ввести не валидный номер телефона из 1 цифры “9”
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об ошибке, поле Телефон заполнено некорректно._

**Негативное тестирование 8.:**
1.	Ввести валидное имя на кириллице в поле Имя “Иван”
2.	Ввести не валидный номер телефона из 15 цифр “799999999999999”
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об ошибке, поле Телефон заполнено некорректно._

**Негативное тестирование 9.:**
1.	Ввести валидное имя на кириллице в поле Имя “Иван”
2.	Ввести буквы кириллицы в поле Телефон “апрарвл”
3.	Нажать на кнопку Записаться

_Ожидаемый результат - Появляется сообщение об ошибке, поле Телефон заполнено некорректно._

 ### 2.Перечень используемых инструментов с обоснованием выбора.

-IDEA - платформа для удобного написание кода и тестов

-Gradle, и Maven - система для установки различных зависимостей

-JUnit - библиотека, для написания автотестов

-CI - система непрерывной интеграции, позволяет отслеживать наличие ошибок, чтобы сборка не упала

-Docker – система для запуска контейнеров с различным содержимым

-Selenide - фреймворк для автоматизированного тестирования, для работы с селекторами

-Git и Github - Система контроля версий, для хранения кодов автотестов

-Faker - генерация случайных тестовых данных

-Jira- инструмент для создания баг-репортов.

 ### 3.Перечень необходимых разрешений, данных и доступов.
При выполнении автоматизированного тестирования сайта необходимо получить разрешение у владельца сайта.
Доступ к API для тестирования через API.
Необходим доступ к БД на чтение, для проверки отправки заявки.

 ### 4.Перечень и описание возможных рисков при автоматизации.

Риск появления проблем с настройкой тестирования, соответствующего окружения и подключения к БД.
Так как в ходе выполнение проекта может измениться структура сайта и имена/наличие локаторов, могут возникнуть при поиске элементов на страницах.

 ### 5.Перечень необходимых специалистов для автоматизации.
QA-engineer
Тестировшик

 ### 6.Интервальная оценка с учётом рисков в часах

36
