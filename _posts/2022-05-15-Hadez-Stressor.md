---
layout: post
title: Hadez Stresser
subtitle: Internet Stresser and Denial of Service Panel (Educational Purposes)
thumbnail-img: /assets/img/hadez.jpg
share-img: /assets/img/hadez_logo.png
cover-img: /assets/img/hadez_login.png
tags: [python]
---
* Stressor and DOS Panel (Code is closed source)

> IP Geolocation

```python
url = requests.get(f"http://www.geoplugin.net/json.gp?ip={IP}").json()
print("\t┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓")
print(f"\t   {IP} Geolocation Information")
print(f"\t   Continent: {url['geoplugin_continentName']}")
print(f"\t   Country: {url['geoplugin_countryName']}")
print(f"\t   Timezone: {url['geoplugin_timezone']}")
print(f"\t   Region/State: {url['geoplugin_regionName']}")
print(f"\t   City: {url['geoplugin_city']}")
print("\t┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛")
```

> Menu

```python
def menu(package, id):
    menu="""
                ┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓                                                        
                ┃         ____   ____       _____        _____        ______      _____                ┃ 
                ┃        |    | |    |  ___|\    \   ___|\    \   ___|\     \    /    /|___            ┃
                ┃        |    | |    | /    /\    \ |    |\    \ |     \     \  /    /|    |           ┃
                ┃        |    |_|    ||    |  |    ||    | |    ||     ,_____/||\____\|    |           ┃ 
                ┃        |    .-.    ||    |__|    ||    | |    ||     \--'\_|/| |   |/    |___        ┃  
                ┃        |    | |    ||    .--.    ||    | |    ||     /___/|   \|___/    /    |       ┃
                ┃        |    | |    ||    |  |    ||    | |    ||     \____|\     /     /|    |       ┃
                ┃        |____| |____||____|  |____||____|/____/||____ '     /|   |_____|/____/|       ┃
                ┃        |    | |    ||    |  |    ||    /    | ||    /_____/ |   |     |    | |       ┃
                ┃        |____| |____||____|  |____||____|____|/ |____|     | /   |_____|____|/        ┃
                ┃          \(     )/    \(      )/    \(    )/     \( |_____|/      \(    )/           ┃
                ┃           '     '      '      '      '    '       '    )/          '    '            ┃
                ┃                                                        '                             ┃
                ┃                    Developed by [REDACTED] | Managed by [REDACTED]                   ┃
                ┃                           https://discord.gg/[REDACTED]                              ┃
                ┣━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┫
                ┃                                                                                      ┃
                ┃           """ + Fore.RED + "[1]. " + Fore.LIGHTRED_EX + """UDP DOS Attack                    """ + Fore.RED + "[2]. " + Fore.LIGHTRED_EX + """Geolocate IP                   ┃     
                ┃                                                                                      ┃                                                               
                ┃                       """ + Fore.RED + "[3]. " + Fore.LIGHTRED_EX + """Ping User ('Ctrl + C' to quit)                            ┃
                ┃                                                                                      ┃
                ┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛
    """
    print(Fore.LIGHTRED_EX + menu.center(width))
    print(r"                Choice: ", end="")
```

{: .box-warning}
**Warning:** Script is closed source and for educational purposes only.