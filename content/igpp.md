+++
author = "coleaderme"
title = "Insta dp Full size!"
date = "2024-05-03"
description = "Download Instagram dp full HD size"
tags = [
	"download",
	"Instagram",
	"Insta",
	"DP",
	"Profile pic"
	"pic",
	"IG",
	"HD",
]
+++

# igpp: Instagram Profile Picture DL  
Download HQ 1080px ig profile picture [github](https://github.com/coleaderme/igpp)  

## Setup  

- `git clone https://github.com/coleaderme/igpp.git`  
- `pip install httpx`  
- `pip install browser_cookie3` (optional)  

0. Login to instagram.com web  
1. Open Developer tools, goto Network Tab (reload [ctrl+r] to capture traffic)  
2. Search for username in IG's search box (eg. apple)   
3. Search "graphql" in Network Tab's search box  
4. Find POST request to /graphql, right click, copy as curl.  
make sure it contains this key:value in payload/data  
`'variables': '{"data":{"context":"blended","include_reel":"true","query":"apple","rank_token":"","search_surface":"web_top_search"},"hasQuery":true}',`   
5. Goto https://curlconverter.com, paste it there   
copy output, paste it in this file `secrets_session.py` (remove first and last line, i.e. import requests and requests.get)  
6. DO NOT share `secrets_session.py`   

Note: this `secrets_session.py` seems to be stop working after sometime (days/hours),  
  try not to get busted by bot detector, use alt account.  
  you may have to redo this everytime your session expires / logs out.  


## Usage:  
- download 'apple' HQ profile pic:  
  `python igpp.py -i apple`  


## Contribute:  
  Any help is appreciated!

