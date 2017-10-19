Prefix = '.'

Token = "YOUR-TOKEN"

Embed_Color = 0xHEX-HERE







### DO NOT EDIT THIS BELOW UNLESS YOU KNOW WHAT YOU ARE DOING ###
import os
from discord.ext import commands
import datetime, re
import json
import discord
import asyncio
import time
import datetime
import random
import aiohttp
import os
import json
import requests
start_time = time.time()


embed_color = Embed_Color
ver = "0.1"
description = "Discord Self Bot"
bot = commands.Bot(command_prefix=Prefix, description=description, pm_help=None, self_bot=True)


@bot.event
async def on_ready():
	print("Logged in!")
	idle = discord.Status.idle
	print("Changed the status to: Idle")
	await bot.change_presence(game=None, status=idle, afk=False)

@bot.command(pass_context = True)
async def stats(ctx):
	second = time.time() - start_time
	minute, second = divmod(second, 60)
	hour, minute = divmod(minute, 60)
	day, hour = divmod(hour, 24)
	week, day = divmod(day, 7)
	embed = discord.Embed(color = embed_color)
	embed.add_field(name="Version", value=ver, inline=False)
	embed.add_field(name="Uptime", value="Weeks: %d, Days: %d, Hours: %d, Minutes: %d"% (week, day, hour, minute), inline=False)
	embed.add_field(name="Prefix", value=Prefix, inline=False)
	embed.set_footer(text="Discord self bot made by Kyousei#8357")
	await bot.say(embed = embed)


@bot.command()
async def shutdown():
	print("Bot shutting down!")
	await bot.logout()

@bot.command(pass_context = True)
async def heart(ctx):
    hearts1 = ["❤", "💞", "💗", "💟", "❣", "♥", "💕", "💓", "💝", "❤💞", "💗💟", "❣♥", "💕💓", "❤💞💗", "💟❣♥", "❤💕💓"]
    hearts2 = ["❤", "💞", "💗", "💟", "❣", "♥", "💕", "💓", "💝", "❤💞", "💗💟", "❣♥", "💕💓", "❤💞💗", "💟❣♥", "❤💕💓"]
    hearts3 = ["❤", "💞", "💗", "💟", "❣", "♥", "💕", "💓", "💝", "❤💞", "💗💟", "❣♥", "💕💓", "❤💞💗", "💟❣♥", "❤💕💓"]
    embed = discord.Embed(description = random.choice(hearts3) + random.choice(hearts2) + random.choice(hearts1), color = embed_color)
    await bot.say(embed = embed)


@bot.command(pass_context = True)
async def ping(ctx):
	pingtime = time.time()
	pingms = await bot.say("Pinging...")
	ping = (time.time() - pingtime) * 1000
	await bot.edit_message(pingms, ":ping_pong: The ping time is `%dms`" % ping)


@bot.command()
async def ud(*msg):
    word = ' '.join(msg)
    api = "http://api.urbandictionary.com/v0/define"
    response = requests.get(api, params=[("term", word)]).json()
    embed = discord.Embed(description = "No results found!", color = 0xFF0000)
    if len(response["list"]) == 0: return await client.say(embed = embed)
    
    embed = discord.Embed(title = "Word", description = word, color = embed_color)
    embed.add_field(name = "Top definition:", value = response['list'][0]['definition'])
    embed.add_field(name = "Examples:", value = response['list'][0]["example"])
    embed.set_footer(text = "Tags: " + ', '.join(response['tags']))
    await bot.say(embed = embed)



@bot.command(pass_context = True)
async def embed(ctx, *, desc: str):
	embed = discord.Embed(description = desc, color = embed_color)
	await bot.say(embed = embed)


bot.run(Token, bot=False)
