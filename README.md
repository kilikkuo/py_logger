# py_logger
A simple logger class for printing out message according to combination of log levels.
By subclassing it and using simple bitwise operation, we can easily to log different messages by levels. 
e.g.

```shellscript
MSG_INFO    = 0x01
MSG_WARNING = 0x02
MSG_ERROR   = 0x04
MSG_VERBOSE = 0x08

LEVEL_ALL     = MSG_INFO | MSG_WARNING | MSG_ERROR | MSG_VERBOSE
LEVEL_ABNORMAL = MSG_WARNING | MSG_ERROR

# Change whatever you want
logger_level = LEVEL_ALL

def logw(msg):
    print("[WARNING] " + msg)
    
def warning(msg):
    global logger_level
    if logger_level & MSG_WARNING:
        logw(msg)

warning(" Watch out here !!")
```
