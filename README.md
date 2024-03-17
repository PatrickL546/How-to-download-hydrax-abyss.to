# New method

# Guide

## Install requirements.txt

`pip install -r requirements.txt`

Not all websites use the same links so you'll have to adapt to that. Hope this helps!

- Browser: Chrome
- Test: https://gojo2.xyz/asre-zero-224-pised/
- Password: nade
- Method also tested on https://voircartoon.com/, https://animet.net/, https://vlist.se/hydrax.html#OHBuc0c4VE41

### Dev tools bypass

- Since this website block right-click or F12, you'll have to find it in the menu

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/2a1f9464-bd91-452a-a868-d4ac407e253a)

- Or use an [extension](https://chromewebstore.google.com/detail/absolute-enable-right-cli/jdocbkpgdakpekjlhemmfcncgdjeiika)

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/1f8eddd0-c20a-4188-87d1-4ede5ad74090)

### Anti-debug bypass

- If a website has anti-debug, turn this on to bypass it and reload

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/1ad57d58-6fd8-41c8-9736-6ee7060d16d5)

### Find cdn ID

- Click the Doc filter to find cdn ID URL. Use filter `?v=`

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/160b0a0c-7b7b-4f48-b6c4-0a2dd3405d1b)

- Get cdn ID. `VswFqVUmq`. ID should be 9 characters

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/a63f88d6-4e6f-4237-bfe0-1692d1a3d315)

# Download

```Python
from base64 import b64decode
from requests import get
from json import loads
from re import search

# cdn_ID. ie. "VswFqVUmq". Note: ID should be 9 characters
cdn_ID = "<cdn_ID>"

# leave empty for 360p
# add "www" for 720p
# add "whw" for 1080p
# if 1080p is not available, it will use the next highest quality
q_prefix = "whw"

domain, vid_id, sources = [loads(b64decode(search(r'PLAYER\(atob\("(.*?)"', get(f"https://abysscdn.com/?v={cdn_ID}").text).group(1)))[i] for i in ["domain","id","sources"]]

print(f"""360p  =  " "  = "sd", "mHd"
720p  = "www" = "hd"
1080p = "whw" = "fullHd"

Available sources {sources}
Downloading "{q_prefix}" or next highest source available
""")

response = get(f"https://{domain}/{q_prefix}{vid_id}", headers={"Referer": f"https://abysscdn.com/?v={cdn_ID}"})
with open("video.mp4", "wb") as f:
    f.write(response.content)
```

# Old method

# [Recommended. Download zip](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/blob/master/Recommended.%20Download%20zip.md)

# [How to create modified .js scripts](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/blob/master/How%20to%20create%20modified%20.js%20scripts.md)

# Guide

## Install requirements.txt

`pip install -r requirements.txt`

Not all websites use the same links so you'll have to adapt to that. Hope this helps!

- Browser: Chrome
- Test: https://gojo2.xyz/asre-zero-224-pised/
- Password: nade
- Method also tested on https://voircartoon.com/, https://animet.net/, https://vlist.se/hydrax.html#OHBuc0c4VE41

### Dev tools bypass

- Since this website block right-click or F12, you'll have to find it in the menu

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/2a1f9464-bd91-452a-a868-d4ac407e253a)

- Or use an [extension](https://chromewebstore.google.com/detail/absolute-enable-right-cli/jdocbkpgdakpekjlhemmfcncgdjeiika)

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/1f8eddd0-c20a-4188-87d1-4ede5ad74090)

### Anti-debug bypass

- If a website has anti-debug, turn this on to bypass it and reload

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/1ad57d58-6fd8-41c8-9736-6ee7060d16d5)

### Find video file name

- Go to network tab and click the Media filter to find the video file name. It should look like this `ce0f5de002c90461a9`. Do not copy `.txt`

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/8847ebab-0239-493e-a6c4-6fa972e478fd)

### Find referrer URL

- Click the Doc filter to find referrer URL. `https://abysscdn.com/?v=VswFqVUmq` this will be used as the referrer
- Note: it will not always be `abysscdn.com` for referrer. It might look like `website.com?v=VswFqVUmq` or it might look like the current URL you're on

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/0fd43709-11da-49f6-8b38-c214691be6a6)

### Find videocdn URL

### If you are using the modified scripts

- Go to Console. Make sure the filter is set to Warnings only and Preserve log is checked

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/3eb8c862-5472-4b2f-8e18-a7e9875207b7)

- It should look like this `mmx9cibe11.globalcdn39.one`. Do not copy `wss://`. Replace it with `https://`

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/f36833d3-9d48-418e-862d-3237d003cb25)

### If you are NOT using the modified scripts

- Click the Websocket filter to find the videocdn URL. You might have to wait for the connection to expire, the site will reconnect and the URL will show up here
- Another way is to disconnect/reconnect internet connection
- It should look like this `sfbhnfiy1.globalcdn39.one`. Do not copy `wss://`. Replace it with `https://`

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/ab6c94c9-3d22-43b2-8291-73b3d6497879)

### Video source picker

Looking at the [bundle.min.js](https://iamcdn.net/players/bundle.min.js). It shows how to get different video sources

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/d74e1668-e56b-4c3b-b44d-e12489093a5c)

- The video file name without any prefix used in the URL is 360p, `www` prefix is 720p, `whw` prefix is 1080p
- `ce0f5de002c90461a9` is 360p
- `www`+`ce0f5de002c90461a9` is 720p
- `whw`+`ce0f5de002c90461a9` is 1080p

# Download

- Combine the video cdn `https://sfbhnfiy1.globalcdn39.one/` with the prefix+video file name `whw`+`ce0f5de002c90461a9` = `https://sfbhnfiy1.globalcdn39.one/whwce0f5de002c90461a9`

Here's an example Python code that downloads each video source

```Python
from requests import get

headers = {"Referer": "https://abysscdn.com/?v=VswFqVUmq"}

url_360p = "https://sfbhnfiy1.globalcdn39.one/ce0f5de002c90461a9"
response = get(url_360p, headers=headers)
with open("video_360p.mp4", "wb") as f:
    f.write(response.content)

url_720p = "https://sfbhnfiy1.globalcdn39.one/wwwce0f5de002c90461a9"
response = get(url_720p, headers=headers)
with open("video_720p.mp4", "wb") as f:
    f.write(response.content)

url_1080p = "https://sfbhnfiy1.globalcdn39.one/whwce0f5de002c90461a9"
response = get(url_1080p, headers=headers)
with open("video_1080p.mp4", "wb") as f:
    f.write(response.content)
```

Here's an empty template

```Python
from requests import get

# referrer_url. ie. "https://abysscdn.com/?v=VswFqVUmq". Note: It will not always look like this
headers = {"Referer": "<referrer_url>"}

# videocdn_url. ie. "sfbhnfiy1.globalcdn39.one". Do not copy wss://
videocdn_url = "https://" + "<videocdn_url>"

# leave empty for 360p
# add "www" for 720p
# add "whw" for 1080p
# if 1080p is not available, it will use the next highest quality
quality_prefix = "whw"

# video_file_name. ie. "ce0f5de002c90461a9".  Do not copy .txt
video_file_name = "<video_file_name>"

url = f"{videocdn_url}{quality_prefix}{video_file_name}"
response = get(url, headers=headers)
with open("video.mp4", "wb") as f:
    f.write(response.content)
```
