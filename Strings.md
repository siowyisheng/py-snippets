# Tricks with strings

### Trim extra spaces in a string

```
" ".join(s.split())
```

### Align/pad strings

```
'{:10}'.format('test') # align left, pad right
'{:>10}'.format('test') # align right, pad left
'{:^10}'.format('test') # align center
```

### Truncate strings

```
'{:.5}'.format('xylophone') # truncate characters
```

### Add sign to numbers

```
'{:+}'.format(42) # +42
'{:+}'.format(-42) # -42
```

### Add sign and padding to numbers

```
'{:=+5d}'.format(23)
```

### Format datetime

```
'{:%Y-%m-%d %H:%M}'.format(datetime(2001, 2, 3, 4, 5))
```

### Parametricized formatting

```
'{:{align}{width}}'.format('test', align='^', width='10')
```
