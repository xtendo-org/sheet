## Max

Get the maximum value without sorting:

```bash
awk '$0>x{x=$0};END{print x}'
```

## Delete matching lines

```bash
sed -i '/pattern/d' file
```

## JPEG manipulation

### Remove EXIF

```bash
jpegtran -copy none -outfile newimage.jpg image.jpg
```

### Lossless rotation

```bash
jpegtran -rotate 90 -outfile newimage.jpg image.jpg
```
