## Level 5

Payload:

```html
javascript:alert(0)
```

When requesting the signup page the backend renders a value passed from client in URL (`level.py`  - line 11):

```python
if "signup" in self.request.path:
        self.render_template('signup.html', {'next': self.request.get('next')}
```

This value is then embedded in the HTML in an `<a>` tag (`signup.html` - line 15):

```
<a href="{{ next }}">Next >></a>
```


["The request object provides a get() method that returns values for arguments parsed from the query and from POST data."](https://webapp2.readthedocs.io/en/latest/guide/request.html)
