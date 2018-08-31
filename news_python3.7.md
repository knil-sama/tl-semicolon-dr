# Source

[what's new in python 3.7](https://docs.python.org/3/whatsnew/3.7.html)
[changelog python 3.7](https://docs.python.org/3/whatsnew/changelog.html)

# tl;dr

+ Solve annotations dependency, calling Class that will be define later by postponing their resolution for last minute.

+ Added a [dataclass](https://docs.python.org/3/library/dataclasses.html) decorator, using it on a class with field will generate by default the magic functions (init, repr, eq, lt, le, gt, ge) can also specifiy if field are hashable or read only

+ Add [contextvars](https://docs.python.org/3/library/contextvars.html), powerful function to create variable that can be access "globally" as long they are still in the context they were set, really useful for asynchronous operation

+ `async` and `await` are now reserved keywords

+ Fix Union bug where Union[ParentClass, ChildrenClass] was simplified to Union[ParentClass].

+ Change handling of [DepreciationWarning](https://docs.python.org/3/whatsnew/3.7.html#whatsnew37-pep565), now it's only displayed when functions containing it are call in __main__ or during test.  
Also add FutureWarning that will alway be displayed by default and PendindDepreciationWarning for test only

+ Now time work with nanoseconds, 6 new \_ns functions are added to use it preperly.

+ New documentation work in Japonese, French and Korean

+ Least but not last datetime object can now convert back iso format with function fromisoformat.

# Afterword

Overall lot of bug fix and improvement for cython and c api and less new features but the focus on asynchronous operations and typing seem to prepare for a safer and more performant python.
