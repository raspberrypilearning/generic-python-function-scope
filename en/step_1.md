Any variable created inside a function is said to be **local** to that function. That is, any code outside of the function won't have access to that variable. For instance here is a simple function:

```python
def say_hello():
    word = "Hello"
	print(word)
```

The variable `word` is local to the function. We say that the variable is in the function's **scope**. That means you can't use that variable outside of the function. For instance, this code causes an error.

```python
def say_hello():
    word = "Hello"
	print(word)

say_hello()
print(word)
```

The variable `word` is outside of the **scope** of the main program - it only exists within the function.

*[global variable]: A **global** variable is a variable declared outside of a function, i.e. within the main program.

It is only possible to change the value of a global variable within a function **if** you tell the function that the variable is global. In this example, changing the value of the variable `word` inside the function has no effect on the variable `word` in the main program. A completely separate copy of the variable has been created and altered within the function:

```python
word = "Goodbye"

def say_hello():
	word = "Hello"
	print("The function thinks that the variable word is:" + word)

say_hello()
print("The main program thinks the variable word is:" + word)
```

However, if you declare the variable `word` to be global within the function, the copy of the variable in the **main program** is edited:

```python
word = "Goodbye"

def say_hello():
    global word
	word = "Hello"
	print("The function thinks that the variable word is:" + word)

say_hello()
print("The main program thinks the variable word is:" + word)
```
--- /step ---
