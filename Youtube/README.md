# How to delete youtube short inside your subscriptions page ?

## Add Tampermonkey extension

TamperMonkey is a chrome extension with which you can run scripts based on your url. 

[Go to chrome extensions](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=fr)

## Create of script

Basically at the creation of your script you have this header :
```js
// ==UserScript==
// @name         New Userscript
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  try to take over the world!
// @author       You
// @match        https://www.deepl.com/translator
// @icon         https://www.google.com/s2/favicons?sz=64&domain=deepl.com
// @grant        none
// ==/UserScript==
```

Change match vaiable by : 
```
@match https://www.youtube.com/feed/subscriptions
```

Now add this code inside your function :
```js
setInterval(() => {
        Array.from(document.querySelectorAll('[overlay-style="SHORTS"]')).map(element => {
                element.parentElement.parentElement.parentElement.parentElement.parentElement.remove()
            })
    }, 1000)
```

Make you sure the scirpt running and go checkou your youtube subscriptions page.
