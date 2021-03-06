Any variable created inside a function is **local** to that function. That is, any code outside of the function won't have access to that variable. Here is a simple function:

```python
def say_hello():
    word = "Hello"
    print(word)
```

The variable `word` is local to this function. We also say that the variable is within the function's **scope**. That means you can't use that variable outside of the function. For instance, this code causes an error:

```python
def say_hello():
    word = "Hello"
    print(word)

say_hello()
print(word)
```

This is because the variable `word` is outside of the scope of the main program — it only exists within the function.

*[global variable]: A **global** variable is a variable declared outside of a function, i.e. within the main program.

You can only change the value of a global variable within a function if you tell the function that the variable is global. In the example below, changing the value of the variable `word` inside the function has no effect on the variable `word` in the main program. A completely separate copy of the variable has been created and altered within the function:

```python
word = "Goodbye"

def say_hello():
    word = "Hello"
    print("The function thinks that the variable word is:" + word)

say_hello()
print("The main program thinks the variable word is:" + word)
```

However, if you declare the variable `word` to be global within the function, the function will edit the copy of the variable in the main program:

```python
word = "Goodbye"

def say_hello():
    global word
    word = "Hello"
    print("The function thinks that the variable word is:" + word)

say_hello()
print("The main program thinks the variable word is:" + word)
```
