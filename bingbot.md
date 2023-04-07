---
layout: page
title: BingBot Discord-Bot
subtitle: Discord Bot hosted by Sparked Host
gh-repo: itsb1ng/BingBot-Discord-Bot
gh-badge: [star, fork, follow]
---
> # BingBot Discord-Bot
> Multifunctional Discord bot that uses many APIs including Hypixel and functional Economy System (Code is not optimized or up-to-date)

> [GitHub Repo](https://github.com/itsb1ng/BingBot-Discord-Bot){: .btn}


> # Accessibility to Slash Commands and Economy System

> - Bot is hosted via SparkedHost and Economy system is loaded to json file on Apollo Server
> - bb!startmining to start the journey
> - /help for all available commands

```python
async def mine(ctx):
  ...
  if account is True:
    with open("storage/premium.json", "r") as premfile:
        premium = json.load(premfile)
    def return_key(val):
      key_list=list(premium[0].keys())
      val_list=list(premium[0].values())
      for i in range(len(premium[0])):
        if val_list[i]==val:
          return key_list[i]
          
    for p in premium[0]:
      for i in range(len(premium[0][p])):
        if ctx.author.user.id == premium[0][p][i]:
          rank_ = return_key(premium[0][p])
    crate = 0
    if data[user_num]['current_pick'] == "BingCoin Pickaxe":
      min = 1
      coin_num = 1
    elif data[user_num]['current_pick'] == "BingCoin Drill": 
      min = 1
      coin_num = 2
    elif data[user_num]['current_pick'] == "Miner x1000": 
      min = 2
      coin_num = 5
```

```python
if (heist_user_num == 0) or (heist_user_num-1 == heist_partner_num) or (heist_user_num+1 == heist_partner_num) or (heist_user_num == heist_partner_num):
      if rank_ == "Script Kitty":
        income_float = income + (income*0.10)
      elif rank_ == "Bitcoin Screenshotter":
        income_float = income + (income*0.15)
      elif rank_ == "NFT Miner":
        income_float = income + (income*0.20)
      income = income_float //2

      
      if rank_ == "Default" and chance <= 20:
        failure = True
      elif rank_ == "Script Kitty" and chance <= 18:
        failure = True
      elif rank_ == "Bitcoin Screenshotter" and chance <= 16:
        failure = True
      elif rank_ == "NFT Miner" and chance <= 14:
        failure = True
      
      if failure is True:
        for x in range(len(data)):
          if data[x]["id"] == ctx.author.id:
            user_num = x
        new_bank = data[user_num]['bank'][0] - income
        outdata = {"id": ctx.author.id, "name": str(ctx.author), "coin": data[user_num]['coin'], "bank": [int(new_bank), data[user_num]['bank'][1]], "spent": data[user_num]['spent'], "current_pick": data[user_num]['current_pick']}
        data.pop(user_num)
        data.append(outdata)
        with open('economy.json', 'w') as out:
          out.write(json.dumps(data))
```


> # Hypixel API 

> - Uses Hypixel's API, Senither API, and SlothPixel API
> - Mostly uses senither because all other APIs are inferior 
> - /help hypixel or bb!help skyblock


```python
@dpy.command()
async def weight(ctx, name):
    try:
        user_name = requests.get(f"https://api.mojang.com/users/profiles/minecraft/{name}").json()
        uuid = user_name["id"]
        profile_link = f"https://api.hypixel.net/skyblock/profiles?key={KEY}&uuid={uuid}"
        sb_data = getInfo(profile_link)
        link = f"https://api.hypixel.net/player?key={KEY}&uuid={uuid}"
        data = getInfo(link)
        senither = f"https://hypixel-api.senither.com/v1/profiles/{uuid}?key={KEY}"
        senither_data = getInfo(senither)
        save = 9999999999999999999
        for x in range(0, len(sb_data['profiles'])):
            for y in sb_data['profiles'][x]['members']:
                if uuid == y:
                    difference = time.time() - sb_data['profiles'][x]['members'][y]['last_save']
                    if difference < save:
                        save = sb_data['profiles'][x]['members'][y]['last_save']
                        profile_id = sb_data['profiles'][x]['profile_id']

        for z in range(0,len(senither_data['data'])):
            if senither_data['data'][z]['id'] == profile_id:
                profile_num = z

        profile_name = data['player']['stats']['SkyBlock']['profiles'][profile_id]["cute_name"]
```

```python
try:
      user_name = requests.get(f"https://api.mojang.com/users/profiles/minecraft/{name}").json()
    except:
      embed=discord.Embed(title="Invalid Username", description="Make sure you spelled the username correctly", color=0xAA4A44)
      embed.set_footer(text=f"Command executed by {ctx.author.name} | Powered by itsb1ng.dev")
      await ctx.send(embed=embed)
      return

    uuid = user_name["id"]
    sb_data = requests.get(f"https://api.hypixel.net/skyblock/profiles?key={KEY}&uuid={uuid}").json()
    profileData = requests.get(f"https://sky.shiiyu.moe/api/v2/profile/{name}").json()
    for i, profileId in enumerate(profileData['profiles']):
      if profileData['profiles'][profileId]['current'] is True:
        profile_id = profileId
        break

    for z in range(0,len(sb_data['profiles'])):
      if sb_data['profiles'][z]['profile_id'] == profile_id:
        profile_num = z

    def number_format(num):
      if num is None:
        format_number = 0
      elif num > 1000000000:
        format = num / 1000000000
        format_number = f"{format:.2f}b"
      elif num > 1000000:
        format = num / 1000000
        format_number = f"{format:.1f}m"
      elif num > 1000:
        format = num / 1000
        format_number = f"{format:.1f}k"
      return format_number
    
    def zero_checker(num):
      if num is None:
        num = 0
      return num

    profile_name = sb_data['profiles'][profile_num]["cute_name"]

    profile = sb_data['profiles'][profile_num]['members'][uuid]

    dict = {"data": profile}

    networth_data = requests.post("https://skyblock.acebot.xyz/api/networth/categories", json=dict).json()
```

{: .box-note}
**Note:** Code was originally created with little experience and was not fully optimized