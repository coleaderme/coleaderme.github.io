+++
title = "Userscripts"
date = "2024-05-30"
description = "You should use Userscipts!"
+++

# Userscripts  
Enhance web experience.

## Without 3rd-party Extention

You don't need external script runner extentions for tasks such as simple redirects..  
1. Create a file `*.user.js` such as: `MyScript.user.js`  
2. Edit and save  
```js
// ==UserScript==
// @name           OldReddit
// @version        1.0
// @namespace      http://example.com
// @description    This script will redirect www.reddit.com to old.reddit.com
// @match          https://www.reddit.com/*
// ==/UserScript==

// some metadata above and actual code below
// OUR ACTUAL CODE
function reddirect(){
  window.location.host = "old.reddit.com";
}
reddirect();
```
**lets breakdown not-so-obvious metadata:**  
`@namespace` leave it to 'https://example.com' know [more](https://stackoverflow.com/questions/386612/what-is-the-greasemonkey-namespace-needed-for)  
`@match` this will match given url pattern and only run this script on those.  

3. Drag-n-drop `MyScript.user.js` to chrome extentions tab.  

{%admonition(type="info")%}
for more advanced use cases 3rd-party Extentions will be required.
{%end%}

## With 3rd-party Extention

Choice of extention: [Violentmonkey](https://violentmonkey.github.io/get-it/)  

- [open source](https://github.com/violentmonkey/)  
- minimal UI  
- [nice documentation](https://violentmonkey.github.io/api/gm/)  
