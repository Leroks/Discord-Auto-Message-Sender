# Discord Bot Setup Guide

A concise guide to configuring and running **DiscordBotStudio** bots with `bot.py`.

---

## Prerequisites

| Requirement                                       | Reason                                          |
| ------------------------------------------------- | ----------------------------------------------- |
| **Python 3.8 or newer**                           | `bot.py` is written for modern Python versions. |
| **Discord Account** (with developer mode enabled) | Needed to fetch IDs and tokens.                 |
| **A text editor / IDE**                           | For editing `bot.py` or `messages_list`.        |

> **Tip**  Enable *Developer Mode* in Discord (Settings ▸ Advanced) to make copying IDs easier.

---

## 1 . Quick Configuration

Run the helper script to collect everything in one go:

```bash
python3 bot.py --setall
```

This will prompt you for the values shown in the table below.

| Field           | Where to find it                | Steps                                                                                                                                                                                                              |
| --------------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **User Agent**  | Your web‑browser                | Copy from your browser’s *about* page or any request header.                                                                                                                                                       |
| **User Token**  | Browser Dev Tools ▸ Network     | 1. Open Discord in a browser and log in.2. Press **F12** (or right‑click ▸ *Inspect*).3. Switch to **Network** tab.4. Send *any* message.5. Select the request and copy the value of the **authorization** header. |
| **Channel URL** | Browser address bar             | Open the target channel and copy the full URL.                                                                                                                                                                     |
| **Channel ID**  | Right‑click channel ▸ *Copy ID* | Developer Mode must be enabled first.                                                                                                                                                                              |

---

## 2 . Manual Configuration (optional)

If you prefer editing directly, open `config.json` (created after `--setall`) and fill in the same values.

---

## 3 . Running the Bot

```bash
python3 bot.py
```

The bot will connect with the stored credentials and begin posting the messages defined in `messages_list`.

---

## 4 . Customising `messages_list`

`messages_list` (inside `bot.py`) is simply a Python list:

```python
messages_list = [
    "Hello world!",
    "Here’s another line.",
    # Add as many messages as you like
]
```

Edit it as you wish—there’s no hard limit.

---

## 5 . Troubleshooting

| Symptom               | Possible Cause                 | Fix                                                          |
| --------------------- | ------------------------------ | ------------------------------------------------------------ |
| ``                    | Wrong or expired *User Token*. | Re‑capture the token via Dev Tools and update `config.json`. |
| ``                    | Missing channel permissions.   | Make sure the account can post in that channel.              |
| Bot exits immediately | Incorrect **Channel ID/URL**   | Verify both values; they must refer to the same channel.     |

---

## 6 . Useful Links

- [Discord Developer Portal](https://discord.com/developers/docs/intro)
- [Discord API Terms](https://discord.com/developers/docs/legal)

---

© 2025 — Happy coding!

