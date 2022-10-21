# bancho.py
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/ambv/black)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/osuAkatsuki/bancho.py/master.svg)](https://results.pre-commit.ci/latest/github/osuAkatsuki/bancho.py/master)
[![Discord](https://discordapp.com/api/guilds/748687781605408908/widget.png?style=shield)](https://discord.gg/ShEQgUx)

peppylnw backend osu server

# Directory Structure
    .
    ├── app                   # the server - logic, classes and objects
    |   ├── api                 # code related to handling external requests
    |   |   ├── domains           # endpoints that can be reached from externally
    |   |   |   ├── api.py        # endpoints available @ https://api.ppy.sh
    |   |   |   ├── cho.py        # endpoints available @ https://c.ppy.sh
    |   |   |   ├── map.py        # endpoints available @ https://b.ppy.sh
    |   |   |   └── osu.py        # endpoints available @ https://osu.ppy.sh
    |   |   |
    |   |   ├── init_api.py       # logic for putting the server together
    |   |   └── middlewares.py    # logic that wraps around the endpoints
    |   |
    |   ├── constants           # logic & data for constant server-side classes & objects
    |   |   ├── clientflags.py    # anticheat flags used by the osu! client
    |   |   ├── gamemodes.py      # osu! gamemodes, with relax/autopilot support
    |   |   ├── mods.py           # osu! gameplay modifiers
    |   |   ├── privileges.py     # privileges for players, globally & in clans
    |   |   └── regexes.py        # regexes used throughout the codebase
    |   |
    |   ├── objects             # logic & data for dynamic server-side classes & objects
    |   |   ├── achievement.py    # representation of individual achievements
    |   |   ├── beatmap.py        # representation of individual map(set)s
    |   |   ├── channel.py        # representation of individual chat channels
    |   |   ├── clan.py           # representation of individual clans
    |   |   ├── collection.py     # collections of dynamic objects (for in-memory storage)
    |   |   ├── match.py          # individual multiplayer matches
    |   |   ├── menu.py           # (WIP) concept for interactive menus in chat channels
    |   |   ├── models.py         # structures of api request bodies
    |   |   ├── player.py         # representation of individual players
    |   |   └── score.py          # representation of individual scores
    |   |
    |   ├── state               # objects representing live server-state
    |   |   ├── cache.py          # data saved for optimization purposes
    |   |   ├── services.py       # instances of 3rd-party services (e.g. databases)
    |   |   └── sessions.py       # active sessions (players, channels, matches, etc.)
    |   |
    |   ├── bg_loops.py           # loops running while the server is running
    |   ├── commands.py           # commands available in osu!'s chat
    |   ├── packets.py            # a module for (de)serialization of osu! packets
    |   └── settings.py           # manages configuration values from the user
    |
    ├── ext                   # external entities used when running the server
    ├── migrations            # database migrations - updates to schema
    ├── tools                 # various tools made throughout bancho.py's history
    └── main.py               # an entry point (script) to run the server
