# RASA Chatbot UI

A lightweight chat widget you can drop into any webpage to connect it to a RASA bot. Supports buttons and image responses in addition to plain text.

![UI screenshot 1](ui1.PNG)
![UI screenshot 2](ui2.PNG)

## Setup

No build step needed — it's plain HTML, CSS, and JavaScript.

1. Make sure your RASA bot is running with the **REST input channel** (not the socketio channel).
2. Open `index.html` in a browser, or serve it with any static file server.
3. Update the RASA server URL in `script.js` to point to your running bot.

Your RASA server needs CORS enabled to accept requests from the page's origin.

## How it works

The widget sends POST requests to:
```
http://localhost:5005/webhooks/rest/webhook
```

Each message includes a `sender` ID and the user's text. Responses come back as a JSON array and the widget renders text, buttons, or images depending on the response type.

## Files

| File | What it is |
|---|---|
| `index.html` | Chat UI markup |
| `script.js` | Message sending + response rendering |
| `style.css` | Widget styles |
| `_config.yml` | GitHub Pages config |

## Connecting to a RASA bot

For the bot side, see the [FAQ-Bot](https://github.com/boluVishal/FAQ-Bot) repo. The REST input channel docs are at rasa.com/docs/core/connectors/#restinput.
