# Flask Telegram Bot API

This is a simple Flask-based API that allows sending messages to a Telegram chat using a bot.

## Features
- Receives `POST` requests with `chat_id` and `update` (message text) in JSON format.
- Sends messages to a specified Telegram chat via the bot.
- Returns success or error messages based on the API response.

## Requirements
Ensure you have Python installed and install the necessary dependencies using:

```sh
pip install -r requirements.txt
```

### Dependencies
- Flask==3.1.0
- requests==2.32.3
- python-dotenv==1.0.1

## Setup
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/flask-telegram-bot.git
   cd flask-telegram-bot
   ```
2. Install dependencies using `pip install -r requirements.txt`.
3. Create a `.env` file in the project root and add your Telegram bot token:
   
   ```sh
   BOT_ACCESS_TOKEN=your_telegram_bot_token_here
   ```

## Usage
Run the Flask app:

```sh
python app.py
```

Send a `POST` request to the endpoint `/submit` with a JSON body:

```json
{
  "chat_id": "123456789",
  "update": "Hello, this is a test message!"
}
```

### Example Request (Using `curl`)
```sh
curl -X POST "http://127.0.0.1:5000/submit" \
     -H "Content-Type: application/json" \
     -d '{"chat_id": "123456789", "update": "Hello from Flask!"}'
```

### Expected Response (Success)
```json
{
  "ok": true,
  "result": {
    "message_id": 1,
    "chat": { "id": 123456789, "type": "private" },
    "text": "Hello from Flask!"
  }
}
```

## Error Handling
- Returns `400` if required fields are missing.
- Returns `500` for unexpected errors.
- If Telegram API fails, returns the error message received from Telegram.

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests.

## License
This project is open-source and available under the MIT License.

## Contact
For any questions, reach out to [your email or GitHub profile link].

