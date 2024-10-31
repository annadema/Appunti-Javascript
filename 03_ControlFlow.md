## Conditional statements

Le istruzioni condizionali consentono di eseguire blocchi di codice alternativi in base ad una condizione.  
JavaScript prevede due istruzioni condizionali: if e switch.

### If

L’istruzione if si presenta in tre forme:

- if semplice
- if con alternativa (if..else)
- if a cascata (if..else if…else)

```javascript
const x = 1;
const y = 2;
// If semplice
if (x == 1) {
  console.log("x è uguale a 1"); //x è uguale a 1
}
// If-else
if (x == y) {
  console.log("x e y sono uguali");
} else {
  console.log("x e y non sono uguali"); //x e y non sono uguali
}
// If a cascata
if (y == 2) {
  console.log("y è uguale a 2"); //y è uguale a 2
  if (y == x) {
    console.log("x e y sono uguali");
  } else {
    console.log("y e x non sono uguali"); //y e x non sono uguali
  }
} else {
  console.log("x e y non sono uguali");
}
```

### Switch

```javascript
switch (x) {
  case 0:
    console.log("x è uguale a 0");
    // L’istruzione break evita il passaggio al case successivo (se il case si verifica)
    break;
  case 1:
    console.log("x è uguale a 1"); //x è uguale a 1'
    break;
  case 2:
    console.log("x è uguale a 2");
    break;
  default:
    console.log("x è diverso da 0 e 1");
    break;
}

switch (6) {
  case 6:
  case 5:
  case 4:
    console.log("non hai vinto medaglie"); //non hai vinto medaglie
    break;
  case 3:
    console.log("hai vinto la medaglia di bronzo");
    break;
  case 2:
    console.log("hai vinto la medaglia d'argento");
    break;
  case 1:
    console.log("hai vinto la medaglia d'oro");
    break;
}
```

### Loops or iteration

Consentono di eseguire un'istruzione ripetutamente.
JavaScript prevede le classiche istruzioni di iterazione:

- while
- do-while
- for (e sue varianti)

### While:

esegue le istruzioni finché si verifica la condizione

```javascript
let z = 0;
while (z < 3) {
  console.log(z); //0 1 2
  z++;
}
```

### Do while:

simile a while ma la condizione viene valutata dopo aver eseguito le istruzioni che quindi vengono eseguite almeno una volta

```javascript
do {
  console.log(z); //3
  z++;
} while (z > 6);
```

### For:

esegue le istruzioni n volte

```javascript
for (let i = 0; i <= 3; i++) {
  console.log("For: " + i);
}
```
