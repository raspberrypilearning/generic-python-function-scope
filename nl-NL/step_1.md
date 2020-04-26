Elke variabele die binnen een functie wordt gemaakt, is **lokaal** voor die functie. Dat wil zeggen, alle code buiten de functie heeft geen toegang tot die variabele. Hier is een eenvoudige functie:

```python
def zeg_hallo():
    woord = "Hallo"
    print(woord)
```

De variabele `woord` is lokaal voor deze functie. We zeggen ook dat de variabele binnen het **bereik** (Engels: scope) van de functie is. Dat betekent dat je die variabele niet buiten de functie kunt gebruiken. Deze code veroorzaakt bijvoorbeeld een fout:

```python
def zeg_hallo():
    woord = "Hallo"
    print(woord)

zeg_hallo()
print(woord)
```

Dit komt omdat de variabele `woord` buiten het bereik van het hoofdprogramma valt - het bestaat alleen binnen de functie.

Je kunt alleen de waarde van een globale variabele binnen een functie wijzigen als je de functie vertelt dat die de variabele globaal is. In het onderstaande voorbeeld heeft het wijzigen van de waarde van variabele `woord` in de functie geen effect op variabele `woord` in het hoofdprogramma. Er is een volledig afzonderlijke kopie van de variabele gemaakt en gewijzigd binnen de functie:

```python
woord = "Tot ziens"

def zeg_hallo():
    woord = "Hallo"
    print("De functie denkt dat de variabele woord is:" + woord)

zeg_hallo()
print("Het hoofdprogramma denkt dat de variabele woord is:"+ woord)
```

Als je echter de variabele `woord` binnen de functie als globaal verklaart, bewerkt de functie de kopie van de variabele in het hoofdprogramma:

```python
woord = "Tot ziens"

def zeg_hallo():
    globaal woord
    woord = "Hallo"
    print("De functie denkt dat de variabele woord is:" + woord)

zeg_hallo()
print("Het hoofdprogramma denkt dat de variabel woord is:" + woord)
```
