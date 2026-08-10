# GMAP Task Board — Railway Deployment

## Files
- bot.py — complete bot source
- requirements.txt — Python dependencies
- railway.toml — Railway build/start/restart configuration
- Procfile — worker fallback
- .env.example — required environment variables

## Railway variables
BOT_TOKEN=<Master BotFather token>
ADMIN_IDS=<numeric Telegram admin ID(s), comma separated>
MAX_USERS_PER_NUMBER=20
DB_PATH=/data/bot.db

## Persistent storage
Attach a Railway Volume and mount it at /data. The bot already defaults to /data/bot.db.
Clone databases, clone logs and the clone encryption key are also kept under the /data tree.

## Start command
python bot.py

## Important
Never commit BOT_TOKEN or clone tokens. Keep the Railway volume attached; deleting/wiping it deletes runtime SQLite data and the clone encryption key.
