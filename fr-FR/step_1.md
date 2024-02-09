Toute variable créée à l'intérieur d'une fonction est **locale** à cette fonction. C'est-à-dire que tout code extérieur à la fonction n'aura pas accès à cette variable. Voici une fonction simple :

```python
def dire_bonjour():
    mot = "Bonjour"
    print(mot)
```

La variable `mot` est locale à cette fonction. On dit aussi que la variable se trouve dans la **portée** de la fonction. Cela signifie que tu ne peux pas utiliser cette variable en dehors de la fonction. Par exemple, ce code provoque une erreur :

```python
def dire_bonjour():
    mot = "Bonjour"
    print(mot)

dire_bonjour()
print(mot)
```

C'est parce que la variable `mot` est en dehors de la portée du programme principal. Elle n'existe qu'à l'intérieur de la fonction.

Tu ne peux modifier la valeur d'une variable globale à l'intérieur d'une fonction que si tu indiques à la fonction que la variable est globale. Dans l'exemple ci-dessous, la modification de la valeur de la variable `mot` à l'intérieur de la fonction n'a aucun effet sur la variable `mot` dans le programme principal. Une copie complètement distincte de la variable a été créée et modifiée dans la fonction :

```python
mot = "Au revoir"

def dire_bonjour():
    mot = "Bonjour"
    print("La fonction pense que la variable word est :" + word)

dire_bonjour()
print("Le programme principal pense que la variable word est :" + word)
```

Cependant, si tu déclares la variable `mot` comme étant globale au sein de la fonction, la fonction modifiera la copie de la variable dans le programme principal :

```python
mot = "Au revoir"

def dire_bonjour():
    mot global
    mot = "Bonjour"
    print("La fonction pense que la variable word est :" + word)

dire_bonjour()
print("Le programme principal pense que la variable word est :" + word)
```
