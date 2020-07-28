Cualquier variable creada dentro de una función es **local** para esa función. Es decir, cualquier código fuera de la función no tendrá acceso a esa variable. Aquí hay una función simple:

```python
def di_hola():
    palabra = "Hola"
    print(palabra)
```

La variable `palabra` es local para esta función. También decimos que la variable está dentro del **alcance** de la función. Esto significa que no puedes usar esa variable fuera de la función. Por ejemplo, este código causa un error:

```python
def di_hola():
    palabra = "Hola"
    print(palabra)

di_hola()
print(palabra)
```

Esto se debe a que la variable `palabra` está fuera del alcance del programa principal — esta solo existe dentro de la función.

Solo puedes cambiar el valor de una variable global dentro de una función si le dices a la función que la variable es global. En el siguiente ejemplo, cambiar el valor de la variable `palabra` dentro de la función no tiene efecto sobre la variable `palabra` en el programa principal. Una copia completamente separada de la variable ha sido creada y alterada dentro de la función:

```python
palabra = "Adiós"

def di_hola():
    palabra = "Hola"
    print("Esta función piensa que la variable palabra es:" + palabra)

di_hola()
print("El programa principal piensa que la variable palabra es:" + palabra)
```

Sin embargo, si declaras que la variable `palabra` es global dentro de la función, la función editará la copia de la variable en el programa principal:

```python
palabra = "Adiós"

def di_hola():
    global palabra
    palabra = "Hola"
    print("La función piensa que la variable palabra es:" + palabra)

di_hola()
print("El programa principal piensa que la variable palabra es:" + palabra)
```
