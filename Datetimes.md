# Tricks with datetimes

### Get week of month

```
from math import ceil

def week_of_month(dt):
    """ Returns the week of the month for the specified date. """
    first_day = dt.replace(day=1)
    dom = dt.day
    adjusted_dom = dom + first_day.weekday()
    return int(ceil(adjusted_dom/7.0))

week_of_month()
```

### Get a date x months from another date.

`dateutil` is an officially recommended package.

```
from datetime import date
from dateutil.relativedelta import relativedelta

six_months = date.today() + relativedelta(months=+6)
```

### Convert from datetime to date

```
today = now.date()
```

### Show datetime as string

Everything other than the % variables are arbitrary.

```
$ now.strftime('%Y-%m-%d %H:%M:%S')
'2018-06-20 20:12:54'
$ now.strftime('It is %A in %B.')
'It is Thursday in June.'
$ now.strftime('The time is %I.%M%p')
```

### Change a datetime

```
now.replace(year=2020,second=0)
```

### Parse a date string

```
$ datetime.datetime.strptime('1988-04-01','%Y-%m-%d')
datetime.datetime(1988, 4, 1, 0, 0)
```

Days and months without leading zeroes also works.

```
$ datetime.datetime.strptime('1988-4-1','%Y-%m-%d')
datetime.datetime(1988, 4, 1, 0, 0)
```

If you just need the date, convert the datetime!

```
$ datetime.datetime.strptime('1988-4-1','%Y-%m-%d').date()
datetime.date(1988, 4, 1)
```
