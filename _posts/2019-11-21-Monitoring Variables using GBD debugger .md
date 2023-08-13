#### Monitoring Variables using GBD debugger 

One development tool I have recently been exposed to is the world of debugging.
Initially, I was introduced to debugging practices in university coursework; however, these lessons only vaguely conveyed their usefulness in practical development.
If my internship at KSC has taught me anything about software engineering, it’s how important the back end of software engineering is.
Between different testing practices, debugging, and formalities, only a sliver of my time spent coding has resulted in production ready code.
These eye-opening experiences have exposed me to debugging practices.   

One of the most common debuggers used the GDB  - or *GNU Debugger*. 
In my case, I’ve used it exclusively the C++ source code, but it’s capabilities are available on many other languages including the entire C family.  Developed in 1986 as part of the GNU family, it has proven to be one of the most popular debuggers commonly available.  

A trivial use case of GNU is to trace a variable though out a program.  This could be done using print statements, but GNU allows for ease of use and simplicity given a minor learning curve.  


##### Example:
Using GDB, it is possible to monitor the value of a variable until a given watchpoint:

watch point on the variable:

```
(gdb) watch var
(gdb) cond <watchpoint_number> var>=value
```

logging to a file:

``` 
(gdb) set logging file <filename> 
(gdb) set logging on 
```

GBD logs default to gdb.txt unless set otherwise


Personally, this ability was extremely useful as I tried to keep track of a counter thought a lengthy ingest sequence. 
In the future I would like to become more comfortable with this tool.
In addition to GNU’s command line ability, my mentor recommended using a GUI-based GNU tool called DDD.
Being able to swiftly and confidently debug is an extremely useful skill that I foresee incredible value in.
