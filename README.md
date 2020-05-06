# Don't run python -m

Try in this repo:

```
 $ python -m http.server
Traceback (most recent call last):
  File "/usr/local/Cellar/python/3.7.7/Frameworks/Python.framework/Versions/3.7/lib/python3.7/runpy.py", line 193, in _run_module_as_main
    "__main__", mod_spec)
  File "/usr/local/Cellar/python/3.7.7/Frameworks/Python.framework/Versions/3.7/lib/python3.7/runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "/usr/local/Cellar/python/3.7.7/Frameworks/Python.framework/Versions/3.7/lib/python3.7/http/server.py", line 90, in <module>
    import copy
  File "/Users/xecycle/local/src/dont-python-m/copy.py", line 1, in <module>
    raise Exception("Are you using python -m http.server?")
Exception: Are you using python -m http.server?
```

```
 $ python -m zipfile -c ../a.zip .
Traceback (most recent call last):
  File "/usr/local/Cellar/python/3.7.7/Frameworks/Python.framework/Versions/3.7/lib/python3.7/runpy.py", line 193, in _run_module_as_main
    "__main__", mod_spec)
  File "/usr/local/Cellar/python/3.7.7/Frameworks/Python.framework/Versions/3.7/lib/python3.7/runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "/usr/local/Cellar/python/3.7.7/Frameworks/Python.framework/Versions/3.7/lib/python3.7/zipfile.py", line 14, in <module>
    import binascii
  File "/Users/xecycle/local/src/dont-python-m/binascii.py", line 1, in <module>
    raise Exception("Don't zip me.  Go away.")
Exception: Don't zip me.  Go away.
```

Use `python -Im` instead.  `-I` disables loading modules from current
working directory, but it is not available in 2.x.
