# Zufall in Unity

## Warum könnte man den Zufall beim Programmieren brauchen?

Um z.B. zufällige Nummern verwenden zu können oder zufällige Namen/Wörter/string; etc. ...  
<br>
## Was ist der Unterschied zwischen Random aus System bzw. aus UnityEngine?

UnityEngine.Random ist eine statische, globale Klasse. Also: __ein__ Generator von Zahlenwerten. Mann kann diese Verwenden, ohne sie vorher deklariert bzw. instanziiert zu haben.  
Hier ein Beispiel dazu:  
<br>
Angenommen wir wollen zufällig ein Level laden.

// Level zufällig auswählen  
int currentLevel = UnityEngine.Random.Range(0, 12);  
// Level laden  
LoadLevel(currentLevel);  
<br>
System.Random muss vor der Verwendung instanziiert bzw. deklariert werden. Man kann eine oder mehrere System.Range instanziieren, wenn man z.B. nicht will, dass ein Generator den anderen nicht beeinflusst.  
<br>
// System.Random-Objekt instanziieren  
System.Random random = new System.Random();  
// Level zufällig auswählen  
int systemCurrentLevel = random.Next(0, 12);  
// Level laden  
LoadLevel(systemCurrentLevel);  
<br>
## Warum ist es sinnvoll bei Random einen Seed zu setzen?
Damit unterschiedliche "Generatoren" die gleiche Sequenz erzeugen. z.B. 2 verschiedene Generatoren mit dem Seed 12 erzeugen die Reihenfolge 1, 4, 9, 25  
<br>
## Was macht Random.Range?
Random.Range gibt einen random float (oder int) Wert zurück, der in (min, max) enthalten ist.
