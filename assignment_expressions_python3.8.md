# Source

[PEP 572 Assignment Expression](https://www.python.org/dev/peps/pep-0572/)

# tl;dr

+ This is a proposal for creating a way to assign to variables within an expression using the notation NAME := expr.

+ Simple example `group = re.match(data).group(1) if re.match(data) else None` can become  
`group = matched.group(1) if matched := re.match(data) else None`

+ In comprehension list `filtered_data = [f(x) for x in data if (y := f(x)) is not None]`  
to `filtered_data = [y for x in data if (y := f(x)) is not None]`

+ For iteration of mutable 

```python
# Compute partial sums in a list comprehension
total = 0
partial_sums = [total := total + v for v in values]
print("Total:", total)
```

+ Fetching specific variables with any and all 

```python
if any((comment := line).startswith('#') for line in lines):
    print("First comment:", comment)
else:
    print("There are no comments")

if all((nonblank := line).strip() == '' for line in lines):
    print("All lines are blank")
else:
    print("First non-blank line:", nonblank)
```

+ Another example with while  

```python
# Loop-and-a-half
while (command := input("> ")) != "quit":
    print("You entered:", command)
```

+ Top level assignement is not valid, `y := f(x)` will not work

# Afterword

Already feel the need for this feature while coding some big comprehension list and can't wait to use is in 3.8.
