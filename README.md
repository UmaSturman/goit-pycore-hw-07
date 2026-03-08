# goit-pycore-hw-07
Консольний бот для керування адресною книгою з підтримкою телефонів та днів народження.

Потрібен Python 3.10+. Сторонні бібліотеки не використовуються.

💬 Команди
КомандаАргументиОписhello—Привітання від ботаadd[ім'я] [телефон]Додати контакт або новий телефон існуючомуchange[ім'я] [старий телефон] [новий телефон]Змінити телефон контактуphone[ім'я]Показати телефони контактуall—Показати всі контактиadd-birthday[ім'я] [ДД.ММ.РРРР]Додати день народженняshow-birthday[ім'я]Показати день народження контактуbirthdays—Список ДН на наступні 7 днівclose / exit—Завершити програму

📋 Приклад використання
Welcome to the assistant bot!
Enter a command: add John 1234567890
Contact added.
Enter a command: add-birthday John 15.03.1990
Birthday 15.03.1990 added to John.
Enter a command: show-birthday John
John's birthday: 15.03.1990
Enter a command: birthdays
John: 15.03.2025
Enter a command: exit
Good bye!

✅ Валідація даних

Телефон — рівно 10 цифр, лише числа
Дата народження — формат ДД.ММ.РРРР
Якщо день народження припадає на суботу або неділю — дата привітання переноситься на понеділок
Усі помилки вводу обробляються з інформативним повідомленням


🏗️ Структура коду
address_book_v2.py
│
├── Field          # Базовий клас для полів
├── Name           # Ім'я контакту (не може бути порожнім)
├── Phone          # Телефон (рівно 10 цифр)
├── Birthday       # Дата народження (формат DD.MM.YYYY)
│
├── Record         # Запис контакту (ім'я + телефони + ДН)
│   ├── add_phone
│   ├── remove_phone
│   ├── edit_phone
│   ├── find_phone
│   └── add_birthday
│
├── AddressBook    # Колекція контактів (UserDict)
│   ├── add_record
│   ├── find
│   ├── delete
│   └── get_upcoming_birthdays
│
└── main()         # CLI-інтерфейс
