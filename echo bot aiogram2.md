#programming #telegrambot

``` python
from aiogram import Bot, Dispetcher, types, executor

bot = Bot('TOKEN')
dp = Dispetvher(bot)

@dp.message_hendler()
async def echo(msg:types.Message):
	await msg.reply(msg.text)
```

### Это простой эхо бот
на aiogram2 
все что он делает это отвечает на сообщение текстом самого же сообщения, не несет особого функционала, но я его тут оставлю для примера
