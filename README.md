# Telegram_bot
import requests
from telegram import Update
from telegram.ext import ApplicationBuilder, CommandHandler, ContextTypes

import os

TOKEN = os.getenv("TOKEN")

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("Bot activo 24/7 ✅")

async def futbol(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("Aquí irán las estadísticas ⚽")

app = ApplicationBuilder().token(TOKEN).build()

app.add_handler(CommandHandler("start", start))
app.add_handler(CommandHandler("futbol", futbol))

print("Bot funcionando...")
app.run_polling()
