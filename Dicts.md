# Tricks with dictionaries

### Proc a variable function:

```
foo_fn = {
    bar: run,
    car: jump,
    jar: hide,
}
foo_fn[foo]()
```

### Create dictionary from lists

```
name_element = {n: e for n, e in zip(names, elements)}
```

### Count elements in values in lists

```
>>> d =  {1: [1, 2, 3], 2: [4, 5]}
>>> sum(map(len, d.values()))
>>> 5
```
