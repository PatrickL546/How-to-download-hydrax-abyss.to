# [Recommended. Download zip](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/blob/master/Recommended.%20Download%20zip.md)

# [How to create modified .js scripts](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/blob/master/How%20to%20create%20modified%20.js%20scripts.md)

# Guide

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

### Anti-debug bypass, working on chrome

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

- You can ignore `#timestamp=`+unix time. If you want to have the timestamp, it looks like this `https://sfbhnfiy1.globalcdn39.one/whwce0f5de002c90461a9#timestamp=1710410059769`

Here's an example Python code that downloads each video source

```Python
import requests

headers = {"Referer": "https://abysscdn.com/?v=VswFqVUmq"}

url_360p = "https://sfbhnfiy1.globalcdn39.one/ce0f5de002c90461a9"
response = requests.get(url_360p, headers=headers)
with open("video_360p.mp4", "wb") as f:
    f.write(response.content)

url_720p = "https://sfbhnfiy1.globalcdn39.one/wwwce0f5de002c90461a9"
response = requests.get(url_720p, headers=headers)
with open("video_720p.mp4", "wb") as f:
    f.write(response.content)

#  It works without the timestamp but here's an example with one
url_1080p = "https://sfbhnfiy1.globalcdn39.one/whwce0f5de002c90461a9#timestamp=1710410059769"
response = requests.get(url_1080p, headers=headers)
with open("video_1080p.mp4", "wb") as f:
    f.write(response.content)
```

Here's an empty template

```Python
import requests

# referrer_url. ie. "https://abysscdn.com/?v=VswFqVUmq". Note: It will not always look like this
headers = {"Referer": "<referrer_url>"}

# videocdn_url. ie. "sfbhnfiy1.globalcdn39.one". Do not copy wss://
videocdn_url = "https://" + "<videocdn_url>"

# leave empty for 360p
# add "www" for 720p
# add "whw" for 1080p
quality_prefix = "whw"

# video_file_name. ie. "ce0f5de002c90461a9".  Do not copy .txt
video_file_name = "<video_file_name>"

# OPTIONAL. timestamp unix time. ie. "#timestamp=1710410059769"
timestamp = ""

url = f"{videocdn_url}{quality_prefix}{video_file_name}{timestamp}"
response = requests.get(url, headers=headers)
with open("video.mp4", "wb") as f:
    f.write(response.content)
```
