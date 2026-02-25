#programming #telegrambot
## тут я покажу работу с фото через aiogram2

```  python
from aiogram import Bot, executor, types, Dispatcher
bot = Bot('your_token')
dp = Dispatcher(bot)
@dp.message_handler()
async def send_photo(message:types.Message):
    with('test.jpg', 'rb') as photo:
        await bot.send_photo(photo=photo, chat_id=message.chat.id)
if __name__ == '__main__':
    executor.start_polling(dp, skip_updates=True)
```

### send_photo
функция для отправки фото файлов через aiogram, только важно то что бы отправить фото важно открыть фото методом 'rb',  функция принимает 2 обязательных аргумента, photo которому должно соответствовать само фото которое вы хотите открыть, и аргумент chat_id который принимает id чата в который вы хотите отправить фото.