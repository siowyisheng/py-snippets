# Tricks with the calendar

### Get a list of month or day names

```
import calendar
for name in calendar.month_name:
  print(name)

for name in calendar.day_name:
  print(name)
```

### Show a month in a calendar

```
print(calendar.TextCalendar(calendar.SUNDAY).formatmonth(2018, 7))

     July 2018
Su Mo Tu We Th Fr Sa
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
29 30 31
```

### Show a full year in a calendar

```
print(calendar.TextCalendar(calendar.SUNDAY).formatyear(2007, 2, 1, 1, 2))
# result omitted for brevity
```

### Get the dates for each first Monday of the month in a year

```
for month in range(1, 13):
    mycal = calendar.monthcalendar(2025, month)
    week1 = mycal[1]
    week2 = mycal[2]
    if week1[calendar.MONDAY] != 0:
        auditday = week1[calendar.MONDAY]
    else:
        auditday = week2[calendar.MONDAY]
        print('{:>10} {:2d}'.format(calendar.month_name[month], auditday))
```
