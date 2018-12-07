# Tricks with lists

### Counting occurrences in a list

```
>>> from collections import Counter
>>> ls = [1,2,3,4,5,5,5]
>>> Counter(ls)
Counter({5: 3, 1: 1, 2: 1, 3: 1, 4: 1})
>>> dict(Counter(ls))
{1: 1, 2: 1, 3: 1, 4: 1, 5: 3}
```
