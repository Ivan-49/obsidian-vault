---
tags:
  - python
  - algorithm
  - telegrambot
language: python
name_lib: aiogram2
type of work: telegram-bot
полезность: 10
создал заметку: 2024-04-23T10:10:00
---

## типы сообщений которые можно обрабатывать через aiogram2

При создании функции для обработки сообщений в нее помимо команды можно указать еще параметр content_type

```python
from aiogram import Bot, Dispetcher, types, executor

bot = Bot('TOKEN')
dp = Dispetvher(bot)

@dp.message_hendler(content_type = ['photo'])
async def echo(msg:types.Message):
	await msg.reply('text')
```


Тут для примера я указал content_type = ['photo']
это значит что теперь эта функция будет срабатывать только если пользователь
отправляет фото
так же есть еще следующие типы содержимого:

- UNKNOWN = 'unknown'
- any = 'any'
- text = 'text'
- animation = 'animation'
- audio = 'audio'
- document = 'document'
- photo = 'photo'
- stocker = 'ctiker'
- story = 'story'
- video = 'video'
- video_note = 'video_note'
- voice = 'voice'
- contact = 'contact'
- dice = 'dice'
- game = 'geme'
- pool = 'pool'
- venue = 'venue'
- new_chat_member = 'new_chat_member'
- left_chat_member = 'left_chat_member'
- new_chat_title = 'new_chat_title'
