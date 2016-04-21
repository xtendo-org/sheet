## Max

Get the maximum value without sorting:

```bash
awk '$0>x{x=$0};END{print x}'
```
