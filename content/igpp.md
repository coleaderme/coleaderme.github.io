+++
title = "Instagram Profile Full Size!"
date = "2024-05-03"
description = "Download Instagram Profile Picture Full HD Size"
+++

# igpp: Instagram Profile Picture DL  
Download HQ 1080px insta profile picture    
![headers](https://raw.githubusercontent.com/coleaderme/coleaderme.github.io/main/static/images/igpp_web.png)  


## Setup  
### CLI version:  
[Download](https://github.com/coleaderme/igpp/archive/refs/heads/main.zip) and unzip  
Run:  
```bash
python igpp.py  apple trevorwallace ...
```

OR  

### Web UI version:  
[Download](https://github.com/coleaderme/igpp-web/archive/refs/heads/main.zip) and unzip  
Run:  
```bash
python run.py  
```


## Requirements 
```bash
pip install httpx
```

**secrets_session.py** *(see below)*  
![headers](https://raw.githubusercontent.com/coleaderme/coleaderme.github.io/main/static/images/igpp_headers.webp)  

*a bit more complicated..*  
0. Login to instagram.com web  
1. Open Developer tools, goto Network Tab ([ctrl+r] reload to capture traffic)  
2. Search for web_profile 'copy as Curl'  
3. Goto https://curlconverter.com, paste it there   
	copy output, paste it in this file `secrets_session.py` (remove first and last line , i.e. `import requests` and `requests.get`)  
DO NOT share `secrets_session.py`   


