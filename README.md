# The Simple Guide to Python

_Python explained simply._

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/siowyisheng/simple-graphql/blob/master/LICENSE) ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

## Table of Contents <!-- omit in toc -->

- [What is Python?](#what-is-python)

## What is Python?

### How do I do profiling in Python?

```python
# for short snippets
>>> import timeit
>>> timeit.timeit('"-".join(str(n) for n in range(100))', number=10000)
0.3018611848820001

# for functions/programs runnable independently
>>> import cProfile
>>> cProfile.run('my_function_to_profile()', globals(), locals())

# for functions run within another system
from profilehooks import coverage, profile, timecall

@coverage # for looking at line coverage
@timecall # for just timing
@profile # for full profiling
def my_function():
    ...
```

```bash
$ python3 -m timeit '"-".join(str(n) for n in range(100))'
10000 loops, best of 5: 30.2 usec per loop
```

### How do I check if a substring exists within a string?

```python
'star' in 'star wars'
# returns True
```

### How do I save the requirements of my current project?

```bash
pip freeze > requirements.txt
```

### How do I write a docstring?

[overflow](https://stackoverflow.com/questions/3898572/what-is-the-standard-python-docstring-format)

### How do I remove all .pyc files in my project?

```bash
find . -name '*.pyc' -delete
```

### How can I run a shell command within Python?

This runs `ls -l` in the shell:

```python
from subprocess import call
call(["ls", "-l"])
```

### How do I merge two dictionaries?

```python
# in place
dict1.update(dict2)

# returned (for python > 3.4)
dict_merged = {**dict1, **dict2}
```

### How do I safely create a nested directory?

```python
import pathlib
pathlib.Path('/my/directory').mkdir(parents=True, exist_ok=True)
```

### How do I create a list of all files in a directory?

```python
from os import listdir
from os.path import isfile, join
onlyfiles = [f for f in listdir(mypath) if isfile(join(mypath, f))]
```

### How do I check if a list is empty?

Empty lists evaluate to `False`.

```python
if not my_list:
  print("List is empty")
```

### How do I access the count within a for loop?

```python
for index, value in enumerate(my_list):
  print(index, value)
```

### How do I check the type of an object?

```python
# returns the type of the object
type(a)

# checks for type inheritance
isinstance(a, SomeType)
```

### Does Python have a ternary operator?

Yes. `a if condition else b` returns a if condition evaluates to True, else b is returned.

### How do I show print messages when running pytest?

```bash
py.test -s my_test.py
```

### How do I use type hints?

[Learn it here.](https://mypy.readthedocs.io/en/latest/cheat_sheet_py3.html#functions)

### Should I group my pytest tests into classes?

There are pros and cons.

Module-level tests have omit the meaningless `self` argument and are flatter.

Grouping tests into classes(one class per class tested in the module) allows us to use the same test name when two classes have the same function name to be tested. It also forces us to group our tests by the class they are testing (and also enables automatic grouping using a text editor).

# python-tricks

Short, useful recipes for various uses in python. Check out the other markdown files for tricks in those categories.

### Alternative data types

```
namedtuple
  for cleaner implementation of objects with only attributes
deque
  for a list-like data type with fast append and prepend
Counter
  for clean counting of objects in a list
```

### Reasonable short variable names for one-use scripts

```
val = 5
ind = 0 # index
[i for i in range(100)]
s = ''
lst = []
lists = [[],[]]
d = {}
tup = ()
with open('myfile.txt','w') as f:
  ...
t = time.time()
dt = datetime.datetime.now()
td = datetime.timedelta(days=1)
heap = []
heapq.heapify(heap)
```

### Naming things

- Use Pronounceable names
- Use Solution Domain Names
- Also Use Problem Domain Names
- Avoid Mental Mapping
- Nothing is intuitive
- Avoid Disinformation
- Names are only Meaningful in Context
- Don't add Artificial Context
- Use plural for a list (burgers = [])
- Use total for a count of objects (total_burger = 0)
