# How to create modified .js scripts

## bundle.min.js

- Go to Dev tools > Network. Click on WS filter then click on bundle.min.js

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/87f76b13-d90a-4314-836b-cef6ebb07549)

- Right click then click on Override content

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/cf23b53a-044a-4c87-921d-9896dc985501)

- It will ask you to select folder, use any folder. Click Allow

- Search for this `new WebSocket(e.url_tunnel`
- Add this after `console.warn("Copy this as videocdn URL:"+e.url);` and Ctrl+S to save

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/42403876-227b-4ad1-acbf-1e9d471674d0)

## playhydrax.min.js

- Find playhydrax.min.js

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/f12cb407-9672-4ce2-b947-c89eb75367af)

- Similar as before
- Right click then click on Override content
- Search for `name:"debugger-checker"`
- Delete isOpen until isEnable

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/2953cd81-c8de-4d2e-8ce4-b81c35240269)

- It should look like this, Ctrl+S to save

![image](https://github.com/PatrickL546/How-to-download-hydrax-abyss.to/assets/75874561/0d124e37-9333-4b39-b18d-c17c8766181c)
