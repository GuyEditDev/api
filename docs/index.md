# Welcome to API Documentation of Discord Python

### Guilds joiner

Request to join a Discord server :
``https://discord.com/api/v6/invite/INVITE_CODE``

*Python code*:
  ```py
import requests


# This function must be updated to handle vanity URL links, but still great for new default invitation links.
def get_invite_code():
    link = input("Discord Invite Link : ")
    if link.__len__() > 8:
        link = link[link.__len__() - 8:]
    return link


def api_request(invite, discord_token):
    endpoint = "https://discord.com/api/v6/invite/" + invite
    r = requests.post(endpoint, headers = {
        "Authorization": discord_token
    })
    return r


def handle_response(response):
    if response.status_code == 200:
        print("Guild successfully joined !")
    elif response.status_code == 403:
        print("The entered token is invalid or expired !")
    else:
        print("The entered invite link is invalid or expired !")
    return None

invite = get_invite_code()
response = api_request(invite, "YOUR_TOKEN")
handle_response(response)
```

<hr>

### Hypesquads

Request to change Hypesquad:
``https://canary.discord.com/api/v9/hypesquad/online``

*Python code*:
```py
import requests
import random


def format_house(color):
    house_id = None
    color = color.lower()
    if color == "purple":
        house_id = 1
    elif color == "red":
        house_id = 2
    elif color == "cyan":
        house_id = 3
    else:
        house_id = random.random(1, 3)
    return { "house_id": house_id }


def api_request(house_data, discord_token):
    endpoint = "https://canary.discord.com/api/v9/hypesquad/online"
    r = requests.post(endpoint, headers = {
        "Authorization": discord_token,
        "Content-Type": "application/json"
    }, json=house_data)
    return r


def handle_response(response):
    if response.status_code == 200:
        print("Hypesquad successfully changed !")
    elif response.status_code == 403:
        print("The entered token is invalid or expired !")
    return None

house_data = format_house("red")
response = api_request(house_data, "YOUR TOKEN")
handle_response(response)
```

Houses table :
| X |   HOUSE   |  COLOR  |
|---|-----------|---------|
| 1 |  Bravery  |  Purple |
| 2 | Brillance |   Red   |
| 3 |  Balance  |  Cyan   |
