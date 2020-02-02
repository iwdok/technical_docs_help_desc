# ТЗ

## Структура БД

![Страуткура БД](https://raw.githubusercontent.com/writerim/technical_docs_help_desc/master/Untitled%20Diagram.png)  

## Шаблон

[Предлагаемый шаблон](http://byrushan.com/projects/sf/1-1/index.html)

* Большой набор готовых элементов
* Простота интеграции
* Простота изменения


## Мобильное приложение сотрудника

* Просмотр списка заявок
* Измение ответственного заявки
* Просмотр и добавление комментариев
* Добавление фото
* Сканирование штрих-кода, QR-code
* Порциоанная отправка кодов
* Передача геоположения о сотруднике
* Пуш уведомления
* Передача статуса работы приложения
* Управление времением в заявке


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

![](http://www.plantuml.com/plantuml/png/bP91JeOm48NtdA8Nu0B66Aw2aPrWWh27kj24XOaR4nDDZ1Teq4P0Mg_mvaPEowAAOdwMl9dlcu4XkQpIighpyoYjgukYpa-pCi83FZ10mv0KyOd0CmPgIN8oGuaZWNieVC9oct5jhbdW7OfkqMF24AqG9tdYfnwQfCzxpndgC3hX8nJpXWtNGMZ_8c3n2hjxm8iFtfYUUUimullQUcqzZl-nRdw79T0OT-lkgFEnua9OSecOkAAMBTGmVkEhwkUfsB-QkFtYK-2W3hpuH0qlA7zVEycAC_w7lW00)



#### Постановка задачи через телефонию
![](http://www.plantuml.com/plantuml/png/TP0z3e9048NxFSLUW0iOOxWAHZh11A47r5XGq5Xhy0He96nMVgxmvaQ-61inDZ3pvkNx0kuszg8u2TRAI-9Dc0HBFrAuei4JZUmne8UHKZiBZOfJ9Zbl7MezqxXWO52mQXdWpijD3h9xhv9fF52ZHyzA1wCnC8J1g2Oemd424uoKvdBaCwK0PrQif5BmRT2G04iWNID7qbabj-LGKc-v_6ePyrkuvgYdvhdpnroHttv0D7yvbEk7A_wo5m00)

#### Уведомление о превышении сроков выполнения
![](http://www.plantuml.com/plantuml/png/TP11IiL038RtEKMMlgKk-nQ-gmXEiL2hsBflBOYWK13tNc4eLWUjqolykP7_r6LvYy0a-UPBoA5kBkwQ--jIreT8XdT4w-p1UYm8-85NVC7RW17Vy7kH8jSJl5gB2RCDYj6UYKQYlvWO8HKNzgCziHZFTzfSkOgVtk1tefe4fygCjBrisgfPMe0pMmhIa5wjuuZ97X7WwGp_6-v9kx9sg_7ik37JZH1pOXaV-AIuJJ9NNHQvy18tjt9WmhFy0G00)
