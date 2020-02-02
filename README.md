# ТЗ

## Структура БД

![Страуткура БД](https://raw.githubusercontent.com/writerim/technical_docs_help_desc/master/Untitled%20Diagram.png)  

## Шаблон

[Предлагаемый шаблон](http://byrushan.com/projects/sf/1-1/index.html)

* Большой набор готовых элементов
* Простота интеграции
* Простота изменения

## Интерфейс и логика работы системы

#### Установка
###### Интерфейс


Форма должна содержать поля ввода:  
Шаг 1:   
* Название БД  
* Логин БД
* Пароль БД
* Адрес БД
* Путь куда сохранить файл

Шаг 2 :  
* Форма регитрации администратора



###### Логика работы
Система проверяет соединени наличия файла конфига, свободен ли порт  
Если нет, то отвечает о том что нужно запустить интерфейс установки  
При каждом старте системы записывает системные записи. Есл они существует, то ничего не делает  

При первоначальной установке проверяет, что система ждет эти параметры и записывает их в файл
После удочной записи нужно перезапустить программу, запустить демон

---

#### Авторизация
###### Интерфейс

Форма должна содержать поля ввода:  
* логин  
* пароль

Кнопки:  
* Вход  
* Вспомнить пароль
* Регистрация

Прочее:  
* При неверной паре логи/пароль показывать уведомление  
* После успешной регистрации перенаправлять пользователя на страницу с личным кабинетом. (страница определяется в настройках системы или пользователя)


###### Логика работы

При получении данных от пользователя, проверять введенные данные. Если данные не верны, отправлять ошибку.  
Если верны, то отдать в ответе апи-токет для дальнейшей работы  

---

#### Регистрация
###### Интерфейс

Форма должна содержать поля ввода:  
* Фамлия   
* Имя  
* Отчество  
* Электронная почта  

Чекбоксы:   
* Согласие на обработку данных 

Кнопки:  
* Регистрация 
* Вход 

###### Логика работы

Копируем настройки системы пользователю
Копируем настройки отображения форм


---

#### Личный кабинет
###### Интерфейс (Шапка)

* События
* Поиск
* Кнопка пользователя
* Кнопка выхода
* Меню




---

#### Компании
###### Интерфейс

* Табы переключения между клиентами
* * Компании
* * Частные лица
* * Контактные лица
* Панель фильтрации
* * Компании
* * * Панель управления строкой
* * * Поля установленные пользователем
* * Физические лица
* * * Панель управления строкой
* * * Поля установленные пользователем
* * Контактные лица
* * * Панель управления строкой
* * * Поля установленные пользователем
* Пастраничный вывод
* Экспорт данных
* Кнопка добавления

Поля по умолчанию:  
* Компании
* * Название
* * Телефон
* * Электронная почта
* * Ответственный менеджер
* * Наблюдатели по умолчанию
* * Дата создания
* Физические лица
* * ФИО
* * Должность
* * Электронная почта
* * Мобильный телефон
* * Права доступа
* * Ответственный менеджер
* * Наблюдатели по умолчанию
* Контактные лица
* * ФИО
* * Должность
* * Электронная почта
* * Мобильный телефон
* * Права доступа
* * Ответственный менеджер
* * Наблюдатели по умолчанию


###### Логика работы

Загружаем данные пользователя по фильтру показываемых полей  
Показываем эти поля и в том порядке.  
Загружаем указанное кол-во строк  

---

#### Договоры
###### Интерфейс

* Табы переключения между клиентами
* * Договоры
* * Сервисные периоды
* Панель фильтрации
* * Договоры
* * * Панель управления строкой
* * * Поля установленные пользователем
* * Сервисные периоды
* * * Панель управления строкой
* * * Поля установленные пользователем
* Пастраничный вывод
* Экспорт данных
* Кнопка добавления


###### Логика работы

Загружаем данные пользователя по фильтру показываемых полей  
Показываем эти поля и в том порядке.  
Загружаем указанное кол-во строк  



## Бизнес логика

#### Постановка задачи

![](http://www.plantuml.com/plantuml/png/SoWkIImgAStDuUAArefLqDMrKmWkIIn9DUI2K60He0oCQwLGaf5Ph014YGh59KMPUUbOPFBoIp9IYs3oC0Kmeusu81JSQ2w7rBmKe1C0)

![src](http://www.plantuml.com/plantuml/uml/SoWkIImgAStDuUAArefLqDMrKmWkIIn9DUI2K60He0oCQwLGaf5Ph014YGh59KMPUUbOPFBoIp9IYs3oC0Kmeusu81JSQ2w7rBmKe1C0)
