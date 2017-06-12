--- step ---
---
title: Scope in Python Function
---

**NOT COMPLETE - PULLED FROM ANOTHER INGREDIENT**
You can have multiple lines of code inside a function if you like, but you should be careful about using variables. Any variable inside a function is said to be **local** to that function. That is, the any code outside of the function won't have access to variable inside the function. For instance here is a simple function:

```python
def say_hello():
    word = "Hello"
	print(word)
```

The variable `word` is local to the function. We say that the variable is in the functions' **scope**. That means you can't use that variable outside of the function. For instance, this code would error.

```python
def say_hello():
    word = "Hello"
	print(word)

say_hello()
print(word)
```

This errors because the variable `word` is outside of the scope of the main program. Here's another example:

```python
word = "Goodbye"

def say_hello():
	print(word)

say_hello()
```

Here, the word `Goodbye` will be printed, as the variable `word` is now a global variable that is in the scope of the main program.

*[global variable]: A **Global** variable is a variable declared outside of a function

Lastly, you can only change the value of a global variable from within a function, if you tell the function that the variable is global. Try these two examples to see the difference:

```python
word = "Goodbye"

def say_hello():
	word = "Hello"
	print("The function thinks that the variable word is:", word)

print(The main program thinks the varible word is:", word)
```

```python
word = "Goodbye"

def say_hello():
	global word
	word = "Hello"
	print("The function thinks that the variable word is:", word)

say_hello()
print(The main program thinks the varible word is:", word)
```
--- /step ---
