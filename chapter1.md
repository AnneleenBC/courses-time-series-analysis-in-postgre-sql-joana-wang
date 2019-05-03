---
title: 'Using Parts of a Date'
description: 'Chapter description goes here.'
free_preview: true
---

## Using Parts of a Date

```yaml
type: VideoExercise
key: 984d436696
xp: 50
```

`@projector_key`
b74e45a133085fdd361db173130ce4d1

---

## Capstone 1

```yaml
type: NormalExercise
key: ae65dc7936
xp: 100
```

You've just been asked by your company to calculate the bonus payments for the year based on sales.
Since you work for a global company, you've received data from different countries but it has come in different formats!
Before you can use the data you need to make sure it's all in consistent formats.

`@instructions`
- `us_sale_date` is currently stored as a string. Make sure you convert it to a date using `TO_TIMESTAMP()`

- `uk_sale_date` is also stored as a string but it is in a different format from `us_sale_date`. Let's convert `uk_sale_date` into a date as well using `TO_TIMESTAMP()`.

- Lastly, `jp_sale_date` is already stored as a date but it was captured in a different time zone! Let's adjust it by subtracting 13 hours.

`@hint`
Make sure the date parts are mapped correctly to the original date.
Do you have quotes around the timestamp format?

`@pre_exercise_code`
```{python}

```

`@sample_code`
```{python}
#Let's convert `us_sale_date` into a date variable
SELECT TO_TIMESTAMP(us_sale_date,---) 
FROM sales

#Let's convert `uk_sale_date` into a date variable
SELECT TO_TIMESTAMP(uk_sale_date,---) 
FROM sales

# Let's adjust `jp_sale_date` by -13 hours
SELECT jp_sale_date - ---
FROM sales
```

`@solution`
```{python}
#Let's convert `us_sale_date` into a date variable
SELECT TO_TIMESTAMP(us_sale_date, 'MM/DD/YYYY HH24:MI:SS') 
FROM sales

#Let's convert `uk_sale_date` into a date variable
SELECT TO_TIMESTAMP(uk_sale_date, 'DD/MM/YYYY HH24:MI:SS') 
FROM sales

# Let's adjust `jp_sale_date` by -13 hours
SELECT jp_sale_date - INTERVAL '13 hours'
FROM sales


```

`@sct`
```{python}

```
