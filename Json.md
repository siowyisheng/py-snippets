# Tricks with json

### Explore json file data

```
import json

with open('pokemon.json','r') as fp:
  d = json.load(fp)
print(json.dumps(d, indent=4))
```
