import discord
from discord.ext import commands

intents = discord.Intents.default()
intents.members = True

bot = commands.Bot(command_prefix=';', intents=intents)

KEYWORD = '/yuna'
ROLE_NAME = 'supporters !!'

@bot.event
async def on_ready():
    print(f'Logged in as {bot.user}')

@bot.event
async def on_member_update(before, after):
    if before.activity != after.activity:
        if isinstance(after.activity, discord.Activity) and after.activity.type == discord.ActivityType.playing:
            if KEYWORD.lower() in after.activity.name.lower():
                role = discord.utils.get(after.guild.roles, name=ROLE_NAME)
                if role:
                    await after.add_roles(role)
                    
                channel = discord.utils.get(after.guild.text_channels, name='／yuna')
                    embed = discord.Embed(
                        description=f"{after.mention} has added **/yuna** to their status ♡",
                        color=discord.Color(0xF1F1F1)
)
                    await channel.send(embed=embed)

bot.run('MTMyNDk3Nzc5MjI2MTI5MjA3Mg.G_agdm.orEzBrFPH1O5RjWDQHvGd7l9i3pvAHC1UkFeYU')
