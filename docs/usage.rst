========
Usage
========

## Creating Images

```python
import discord
from discord.ext import commands
import canvacord

client = commands.Bot(command_prefix="!")

@client.comand()
async def rankcard(ctx):
    user = ctx.author
    username = ctx.author.name + "#" + ctx.author.discriminator
    currentxp = 1
    lastxp = 0
    nextxp = 2
    current_level = 1
    current_rank = 1
    background = None
    image = await canvacord.rankcard(user=user, username=username, currentxp=currentxp, lastxp=lastxp, nextxp=nextxp, level=current_level, rank=current_rank, background=background)
    file = discord.File(filename="rankcard.png", fp=image)
    await ctx.send(file=file)

@client.comand()
async def triggered(ctx):
    user = ctx.author
    image = await canvacord.trigger(user)
    file = discord.File(filename="triggered.gif", fp=image)
    await ctx.send(file=file)

@client.comand()
async def communism(ctx):
    user = ctx.author
    image = await canvacord.communism(user)
    file = discord.File(filename="communism.gif", fp=image)
    await ctx.send(file=file)

@client.comand()
async def jail(ctx):
    user = ctx.author
    image = await canvacord.jail(user)
    file = discord.File(filename="jail.png", fp=image)
    await ctx.send(file=file)

@client.comand()
async def gay(ctx):
    user = ctx.author
    image = await canvacord.gay(user)
    file = discord.File(filename="gay.png", fp=image)
    await ctx.send(file=file)
    
client.run("BOT_TOKEN")
```