# Проект "UniHelper"
## Программа для автоматизированного создания заметок
Программа, которая помогает студентам эффективно работать с большим объемом
информации и литературы. Приложение предоставляет возможность создавать
заметки, фиксировать важные моменты и идеи по книгам и темам.

Телеграм-бот для преобразования текста в звук и обратно
Ссылка на телеграм-бот https://t.me/MyUNHelpBot
![OIG.jpeg](https://github.com/santerr80/UniHelper/blob/main/OIG.jpeg)

### Начало работы:
#### Описание:
```# https://t.me/MyUNHelpBot

import telebot

from telebot import types

bot = telebot.TeleBot('6920375156:AAEKC-Q4hiZRNLBWS2IOT4r_2LVse13D9gU')

@bot.message_handler(commands=["start"])
def main(message):
    bot.send_message(message.chat.id, f'Привет, <b>{message.from_user.first_name}</b>!', parse_mode='html')


@bot.message_handler(commands=["help"])
def main(message):
    bot.send_message(message.chat.id, "<b>Справка по функциям бота</b>", parse_mode='html')
    

@bot.message_handler(content_types=["voice"])
def get_voice(message):
    markup = types.InlineKeyboardMarkup()
    markup.add(types.InlineKeyboardButton("Напечатать сообщение в виде текста", callback_data="convert to text"))
    bot.send_message(message.chat.id, 'Выберите действие', reply_markup=markup)
    
@bot.message_handler(content_types=["text"])
def get_text(message):
    markup = types.InlineKeyboardMarkup()
    markup.add(types.InlineKeyboardButton("Озвучить текст", callback_data="convert to voice"))
    bot.reply_to(message, 'Выберите действие', reply_markup=markup)

bot.polling(none_stop=True)
```
Данный код представляет собой пример простого телеграм-бота, написанного на Python
с использованием библиотеки telebot. Бот реагирует на команды /start и /help, а также
обрабатывает голосовые и текстовые сообщения, предлагая пользователю различные варианты действий.
#### Установка:
Для работы с данным кодом необходимо установить библиотеку telebot. Это можно сделать с помощью pip:
```pip install pyTelegramBotAPI```
#### Использование:
-  Зарегистрируйте нового бота в Telegram через @BotFather и получите токен.
-  Вставьте токен в строку ```bot = telebot.TeleBot('YOUR_TOKEN_HERE')``` .
-  Запустите код.
#### Функционал:
- При получении команды /start бот отправляет приветственное сообщение с именем пользователя.
- При получении команды /help бот отправляет справку по функциям.
- При получении голосового сообщения бот предлагает конвертировать его в текст.
- При получении текстового сообщения бот предлагает озвучить его.
#### Запуск:
Для запуска бота необходимо вызвать метод:
``` bot.polling(none_stop=True) ```
#### Требования к окружению:
- Python 3.x
- Библиотека telebot
### Основные функции приложения:
Создание заметок, приложение предоставляет удобный интерфейс, который
позволяет создавать заметки с помощью печатного ввода или голосового ввода
с автоматическим переводом в текстовый формат. Это
дает возможность быстро и удобно запечатлеть все важные моменты и идеи,
даже если у вас нет возможности печатать.
Организация заметок существующие заметки автоматически сортируются по
темам и книгам, что позволяет быстро находить нужную информацию.Можно
просматривать заметки в текстовом формате или воспроизводить их в аудио
формате. Это делает процесс повторения и освоения материала более удобным и
эффективным.


### Команда проекта
- **Менеджер проекта/Scrum-мастер:** Красильников М.Н.
- **Аналитик данных/Data Scientist:** Колегов В.С.
- **Инженер по машинному обучению (ML Engineer):** Ибатулин А.А. 
- **Full Stack-разработчик:** Горбунов А.В.
- **Тестировщик-QA инженер:** Черенков К.Н. 
- **Документалист/технический писатель:** Тимонин И.Л., Бондаренко Н.А.
### Лицензия
![LICENSE](https://github.com/santerr80/UniHelper/blob/main/LICENSE)
