<p align="center">
  <img width="100" src="https://raw.githubusercontent.com/fosscord/fosscord/master/assets/logo_big_transparent.png" />
</p>
<h1 align="center">Fosscord Python API Wrapper</h1>

<p align="center">
   <a href="https://discord.gg/ZrnGQP6p3d">
    <img src="https://img.shields.io/discord/806142446094385153?color=7489d5&logo=discord&logoColor=ffffff" />
  </a>
  <img src="https://img.shields.io/static/v1?label=Status&message=Development&color=blue">
  <a title="Crowdin" target="_blank" href="https://translate.fosscord.com/"><img src="https://badges.crowdin.net/fosscord/localized.svg"></a>
  <a href="https://opencollective.com/fosscord">
    <img src="https://opencollective.com/fosscord/tiers/badge.svg">
  </a>
</p>
<p align="center">
  A modern, easy to use, feature-rich, and async ready API wrapper for Fosscord written in Python. This build is a WIP and may be considered as unfinished and unstable.
</p>
<p align="center">
  <a href="https://discord.gg/BBuHyBQwe3"><strong>Community Discord Server</strong></a>
</p>

## Key Features

- Modern Pythonic API using ``async`` and ``await``.
- Proper rate limit handling.
- 100% coverage of the supported Discord API.
- Optimised in both speed and memory.

## Installing

**Python 3.8 or higher is required**

To install the library without full voice support, you can just run the following command:

```sh
# Linux/macOS
python3 -m pip install -U fosscord.py

# Windows
py -3 -m pip install -U fosscord.py
```

To install the development version, do the following:

```sh
$ git clone https://github.com/fosscord/fosscord.py
$ cd fosscord.py
$ python3 -m pip install -U .[voice]
```

## Optional Packages

- [PyNaCl](https://pypi.org/project/PyNaCl) (for voice support)

Please note that on Linux installing voice you must install the following packages via your favourite package manager (e.g. `apt`, `dnf`, etc) before running the above commands:

- `libffi-dev` (or `libffi-devel` on some systems)
- `python-dev` (e.g. `python3.6-dev` for Python 3.6)

## Examples

### Classic

```py
import fosscord

class MyClient(fosscord.Client):
  async def on_ready(self):
  print('Logged on as', self.user)

  async def on_message(self, message):
    # don't respond to ourselves
    if message.author == self.user:
      return

    if message.content == 'ping':
      await message.channel.send('pong')

client = MyClient()
client.run('token')
```

### Bot

```py
import fosscord
from fosscord.ext import commands

bot = commands.Bot(command_prefix='>')

@bot.command()
async def ping(ctx):
  await ctx.send('pong')

bot.run('token')
```

### Note

You can find more examples in the examples directory.

## Links

- [Discord.py Documentation](https://discordpy.readthedocs.io/en/latest/index.html)
- [Official Discord.py Server](https://discord.gg/r3sSKJJ)
- [Discord API](https://discord.gg/discord-api)
