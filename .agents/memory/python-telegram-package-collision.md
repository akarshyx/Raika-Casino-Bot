---
name: Python Telegram package collision
description: Avoid the unrelated telegram distribution when installing python-telegram-bot.
---

The project must install `python-telegram-bot` without the separate PyPI package named `telegram`; the two distributions share the `telegram` module, and the unrelated package can overwrite the correct package initializer.

**Why:** The collision makes imports such as `InlineKeyboardButton` fail even when `python-telegram-bot` is installed.

**How to apply:** Keep `telegram` out of dependency files. If the module is corrupted after installation, remove the unrelated distribution and reinstall `python-telegram-bot`.