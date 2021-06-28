## Welcome to API Documentation of Discord Python

You can use the [editor on GitHub](https://github.com/GuyEditDev/api/edit/index/docs/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Joiner Server

Requests for join a server:
  Discord API: https://discordapp.com/api/v6/invite/ + link of server
  Code Python:
  ```markdown
  import requests

  link = input('Discord Invite Link: ')
  if len(link) > 6:
      link = link[19:]
  apilink = "https://discordapp.com/api/v6/invite/" + str(link)

  print (link)
  headers={
  'Authorization': "YOUR TOKEN"
  }
  requests.post(apilink, headers=headers)
  ```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Team Hypesquad Requests

Requests to join hypesquad team:
  Discord API: https://canary.discord.com/api/v9/hypesquad/online
  Code Python:
  ```markdown
  from os import system
  from requests import post
  system("cls")
  data = {
      "house_id": 1
  }
  header = {
      'Authorization': "YOUR TOKEN",
      'Content-Type': 'application/json'
  }
  r = post("https://canary.discord.com/api/v9/hypesquad/online", headers = header, json = data)
  ```
  1: Bravery HypeSquad (Purple)
  2: Brillance de la HypeSquad (Red) 
  3: Balance de la HypeSquad (Cyan)


Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/GuyEditDev/api/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.


```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```
