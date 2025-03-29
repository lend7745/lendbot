import requests

# Bot credentials
TOKEN = "7587158015:AAHHuz5z6HS3lgL_o-h7Y2PuV7ZTnnXhWE0"
CHAT_ID = "7871635702"

# Telegram API URL
URL = f"https://api.telegram.org/bot{TOKEN}/sendMessage"

# Main menu message settings
payload = {
    "chat_id": CHAT_ID,
    "text": "🔝 Main Menu\nChoose an option below:",
    "parse_mode": "Markdown",
    "reply_markup": {
        "keyboard": [
            [{"text": "APPLY FOR A LOAN"}],
            [{"text": "ANNOUNCEMENT"}],
            [{"text": "SUPPORT"}]
        ],
        "resize_keyboard": True,
        "one_time_keyboard": False
    }
}

# Send the request to Telegram
response = requests.post(URL, json=payload)
print(response.json())
