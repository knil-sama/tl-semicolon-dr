# Source

[Video by Marc Garcia](https://www.youtube.com/watch?v=kUloTjPPgzU)

# tl;dr

+ [Integration with scikit-learn](https://youtu.be/kUloTjPPgzU?list=WL&t=1653), sklearn.compose can be used to create column transformer to be integrated in sklearn.pipeline.

+ [Extending pandas](https://youtu.be/kUloTjPPgzU?list=WL&t=1389) cyberpanda [official repo](https://github.com/ContinuumIO/cyberpandas) example of using [extending pandas](http://pandas-docs.github.io/pandas-docs-travis/extending.html#extension-types).

+ [Fletcher use](https://youtu.be/kUloTjPPgzU?list=WL&t=1551), another example of a [tool](https://github.com/xhochy/fletcher) using extensionArray interface that allows to use arrow columns in pandas dataframe with multiple benefits (debug information, random data generation, etc ...)

```python
import fletcher as fr
import pandas as pd

df = pd.DataFrame({
    'str_column': fr.FletcherArray(['Test', None, 'Strings'])
})
df.info()

# <class 'pandas.core.frame.DataFrame'>
# # RangeIndex: 3 entries, 0 to 2
# # Data columns (total 1 columns):
# # str_column    2 non-null string
# # dtypes: string(1)
# # memory usage: 108.0 bytes
```

+ [Little assign trick](https://youtu.be/kUloTjPPgzU?list=WL&t=1168), in python3 you can use a created value in the same assign right after creation.

+ [Inplace param deprecation](https://youtu.be/kUloTjPPgzU?list=WL&t=352), to foster more "functionnal" data pipeline based on chaining of assign, map, apply, etc ...

+ [Lazy evaluation](https://youtu.be/kUloTjPPgzU?list=WL&t=598), in pandas use nlargest instead of sort and head for more perf.

+ [Mentions cool projects for efficient high level operation](https://youtu.be/kUloTjPPgzU?list=WL&t=677), like dask for distributed computation, [Ibis](https://docs.ibis-project.org/) a abstractor for SQL and storage plateform.

+ [Arrow](https://youtu.be/kUloTjPPgzU?list=WL&t=1047), the solution for pandas memory perf in the futur, fletcher give a nice introduction to what this futur will be.

+ [Kernel Density Estimate](https://youtu.be/kUloTjPPgzU?list=WL&t=1611), new [pandas.Series.plot.kde](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.plot.kde.html) added during a spring, that can be useful for supervised learning like SVM to normalize input.

# Afterword

+ Pandas'community recognize the current memory backend limitation and prepare for a switch to arrow in the futur, but you already can use Fletcher in your project :astonished: .

+ Even if most of the API stay the same you better don't forgot to check for new features.

+ I got another nail the coffin to my use of inplace :grimacing:.
