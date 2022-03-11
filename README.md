# Bot-for-Telegram
import telebot
from telebot import types # для указание типов
import config

bot = telebot.TeleBot('5275456111:AAH6J7cEMQGaaZQkGMUwto2uj71SE0wo3fg')

@bot.message_handler(commands=['start'])
def start(message):
    markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
    btn1 = types.KeyboardButton("Информация")
    btn2 = types.KeyboardButton("Дискорд [14+]")
    btn3 = types.KeyboardButton("Беседа в ВКонтакте[14+]")
    btn4 = types.KeyboardButton("Беседа в Телеграм [14+]")
    btn5 = types.KeyboardButton("Сливки [16+]")
    btn6 = types.KeyboardButton("Связь с Администрацией")
    btn7 = types.KeyboardButton("В разработке...")

    markup.add(btn1, btn2, btn3, btn4, btn5, btn6)
    bot.send_message(message.chat.id, text="Привет, {0.first_name}! Я бот AE squad".format(message.from_user), reply_markup=markup)
    
@bot.message_handler(content_types=['text'])
def func(message):
    if(message.text == "Информация"):
        bot.send_message(message.chat.id, text="Добро пожаловать в AE squad BOT ,этот бот предназнчет для того чтобы вы могли найти месточко для общения ")

    if(message.text == "Дискорд [14+]"):
        bot.send_message(message.chat.id, text="Дискорд сервер AE squad\nhttps://diskord.gg/5rfmvwd3uz")

    if(message.text == "Беседа в ВКонтакте[14+]"):
        bot.send_message(message.chat.id, text="Беседа AE squad в ВК\nhttps://vk.me/join/AJQ1d45dASBTw27tq1_NN67p")
    
    if(message.text == "Беседа в Телеграм [14+]"):
        bot.send_message(message.chat.id, text="Беседа AE squad в Телеграам:t.me/+Lq9Uz8XMstwzYWYy")
       
    if(message.text =="Сливки [16+]"):
        bot.send_message(message.chat.id, text="Беседа в Телеграмм для Знакомств Сливки [16+] t.me/odessa_manga")
    
    if(message.text =="Связь с Администрацией"):
        bot.send_message(message.chat.id, text="Главный Администратор @Wi_Vi_V")

bot.polling(none_stop=True)
