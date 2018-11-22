## Level 1

Payload: 

```
<script>alert(0);</script>
```

No input validation or sanitation in line 45:

```
message = "Sorry, no results were found for <b>" + query + "</b>."
```