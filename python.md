## Password

In case the service doesn't understand security and won't let you use a strong and [human-memorable] password, you have no choice but to:

```python
''.join(random.choice('ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789') for _ in range(15))
```

Adjust the string part and the number to match the service's (dumb) requirement.

[human-memorable]: https://xkcd.com/936/
