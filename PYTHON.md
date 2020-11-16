## Optimize Python code

### Line-by-line timing and execution frequency with a profiler

> pip install line_profiler

```
@profile
def primes(n):
    if n == 2:
        return [2]
    elif n < 2:
        return []
    s = range(3,n+1,2)
    mroot = n ** 0.5
    half = (n+1)/2-1
    i = 0
    m = 3
    while m <= mroot:
        if s[i]:
            j = (m*m - 3)/2
            s[j] = 0
            while j < half:
                s[j] = 0
                j += m
        i = i + 1
        m = 2*i + 3
    return [2] + [x for x in s if x]

primes(100)
```

Once you’ve gotten your code setup with the @profile decorator, use kernprof.py to run your script.

> kernprof.py -l -v fib.py

### How much memory does it use?

> pip install -U memory_profiler
> pip install psutil

```
@profile
def primes(n):
    ...
    ...
```

To see how much memory your function uses run the following:

> python -m memory_profiler primes.py

### Where’s the memory leak?

> pip install objgraph

Once you have this tool installed, insert into your code a statement to invoke the debugger:

> import pdb; pdb.set_trace()

Reference: [Python performance analysis](https://everyhue.me/posts/python-performance-analysis/)