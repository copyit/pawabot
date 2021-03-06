# pawabot

[![ci](https://github.com/pawamoy/pawabot/workflows/ci/badge.svg)](https://github.com/pawamoy/pawabot/actions?query=workflow%3Aci)
[![documentation](https://img.shields.io/badge/docs-mkdocs%20material-blue.svg?style=flat)](https://pawamoy.github.io/pawabot/)
[![pypi version](https://img.shields.io/pypi/v/pawabot.svg)](https://pypi.org/project/pawabot/)

My personal Telegram bot: aria2 management, torrent sites crawling, media organization with mvodb and Plex, etc.

This bot provides a command to search for torrents on the web, and let you select them for download.
There is a basic permission system allowing to manage multiple users for one bot.

## Requirements

pawabot requires Python 3.6 or above.

<details>
<summary>To install Python 3.6, I recommend using <a href="https://github.com/pyenv/pyenv"><code>pyenv</code></a>.</summary>

```bash
# install pyenv
git clone https://github.com/pyenv/pyenv ~/.pyenv

# setup pyenv (you should also put these three lines in .bashrc or similar)
export PATH="${HOME}/.pyenv/bin:${PATH}"
export PYENV_ROOT="${HOME}/.pyenv"
eval "$(pyenv init -)"

# install Python 3.6
pyenv install 3.6.12

# make it available globally
pyenv global system 3.6.12
```
</details>

## Installation

With `pip`:
```bash
python3.6 -m pip install pawabot
```

With [`pipx`](https://github.com/pipxproject/pipx):
```bash
python3.6 -m pip install --user pipx

pipx install --python python3.6 pawabot
```

## Setup

1. Create your Telegram bot account by talking to the `@botfather` bot.
2. Write your bot token in `~/.config/pawabot/bot_token.txt`,
   or set and export the environment variable `BOT_TOKEN`.
3. Register your Telegram main account as administrator in the database with:

```
pawabot create-admin -i MY_TG_ID -u MY_TG_USERNAME
```

## Usage

```
usage: pawabot [-h] [-L {TRACE,DEBUG,INFO,SUCCESS,WARNING,ERROR,CRITICAL}]
               ...

optional arguments:
  -h, --help            show this help message and exit

Commands:
  
    run                 Run the bot.
    create-admin        Create an administrator in the database.
    create-user         Create a user in the database.
    list-users          List registered users.

Global options:
  -L {TRACE,DEBUG,INFO,SUCCESS,WARNING,ERROR,CRITICAL}, --log-level {TRACE,DEBUG,INFO,SUCCESS,WARNING,ERROR,CRITICAL}
                        Log level to use
```

Commands:

- [`create-admin`](#create-admin)
- [`create-user`](#create-user)
- [`list-users`](#list-users)
- [`run`](#run)


### `create-admin`

```
usage: pawabot create-admin [-h] [-i UID] [-u USERNAME]

Create an administrator in the database.

optional arguments:
  -h, --help            Show this help message and exit.
  -i UID, --uid UID     Telegram user id.
  -u USERNAME, --username USERNAME
                        Telegram user name.
```

### `create-user`

```
usage: pawabot create-user [-h] [-i UID] [-u USERNAME] [-a]

Create a user in the database.

optional arguments:
  -h, --help            Show this help message and exit.
  -i UID, --uid UID     Telegram user id.
  -u USERNAME, --username USERNAME
                        Telegram user name.
  -a, --admin           Give admin access.
```

### `list-users`

```
usage: pawabot list-users [-h]

List registered users.

optional arguments:
  -h, --help  Show this help message and exit.
```

### `run`

```
usage: pawabot run [-h]

Run the bot.

optional arguments:
  -h, --help  Show this help message and exit.
```

## Screenshots

/start | /help | /search
------ | ----- | -------
![start](img/start.jpg) | ![help](img/help.jpg) | ![search](img/search.jpg)
