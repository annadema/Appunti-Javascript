## variabili

Le variabili consentono di salvare in memoria temporanea i valori dei dati da elaborare

In JavaScript, è possibile dichiarare le variabili in tre modi:

- var
- let
- const (valori costanti)

N.B. JavaScript distingue tra lettere maiuscole e minuscole.

## identificatori

In JavaScript, gli identificatori vengono utilizzati per denominare costanti, variabili, proprietà,
funzioni e classi e per fornire etichette per determinati cicli del codice JavaScript.

Un identificatore deve iniziare con una lettera, un underscore (\_) o un segno di dollaro ($).
I caratteri successivi possono essere lettere, cifre, trattini bassi o segni di dollaro.

## Tipi principali di dati JavaScript

```javascript
const myString = "Aldo";
const myNumber = 33.05;
const myBoolean = true;
```

### Oggetto JSON (JavaScript Object Notation):

raccolta non ordinata di valori dotati di un nome

```javascript
const myObject = { name: "Aldo", surname: "Rossi", age: 33 };
```

### Array

tipo speciale di oggetto che rappresenta una raccolta ordinata di valori numerati

```javascript
const myArray = ["Aldo", "Giovanni", "Giacomo"];
```

### Altri tipi Javascript:

Map, Set, RegExp, Date, Error...

### Map

insieme di valori, le chiavi, dove a ogni chiave è associato (o “mappato”) un altro valore (array indicizzato)

```javascript
const myMap = new Map([
  [1, "Aldo"],
  ["Due", "Giovanni"],
  ["User", { name: "Giacomo", surname: "Verdi", age: 33 }],
]);
```

### Set:

insieme non ordinato o indicizzato, non consente l’esistenza di duplicati

```javascript
const mySet = new Set("Fuggifuggi");
```

### null

è un valore di assegnazione: può essere utilizzato per assegnare esplicitamente nessun valore

```javascript
const myNull = null;
```

### undefined:

valore che il compilatore JS imposta automaticamente per variabili senza assegnazione

```javascript
let myUndefined;
```

Es.
Scrivi il codice precedente in un tag script per vedere il valore di ogni variabile nella console del browser

```html
<script>
  const myString = "Aldo";
  const myNumber = 33.05;
  const myBoolean = true;
  const myObject = { name: "Aldo", surname: "Rossi", age: 33 };
  const myArray = ["Aldo", "Giovanni", "Giacomo"];
  const myMap = new Map([
    [1, "Aldo"],
    ["Due", "Giovanni"],
    ["User", { name: "Giacomo", surname: "Verdi", age: 33 }],
  ]);
  const mySet = new Set("Fuggifuggi");
  const myNull = null;
  let myUndefined;

  console.log(myString);
  console.log(myNumber);
  console.log(myBoolean);
  console.log(myObject);
  console.log(myArray);
  console.log(myMap);
  console.log(mySet);
  console.log(myNull);
  console.log(myUndefined);
</script>
```

I valori assegnati a una costante non possono essere modificati  
 I valori const devono essere dichiarati e inizializzati allo stesso tempo

```javascript
const MYCONST = "Mia costante";
MYCONST = "Mia costante"; //ERRORE
const MYCONST2; //ERRORE
console.log(MYCONST);
```

i valori assegnati a una costante non possono essere modificati  
i valori const devono essere dichiarati e inizializzati allo stesso tempo  
Sebbene i valori const non possano essere riassegnati, essi sono di tipo **mutable**
in quanto è possibile modificare le proprietà degli oggetti dichiarati const.

```javascript
const MYOBJ = {
  name: "Aldo",
  surname: "Rossi",
  age: 33,
};
console.log(MYOBJ);
```

Ok: modifica le proprietà dell'oggetto, non l'oggetto

```javascript
MYOBJ.name = "Ciro";
MYOBJ.surname = "Verdi";
MYOBJ.age = 44;
console.log(MYOBJ);
```

Errore: assegna un nuovo valore oggetto (anche se con gli stessi valori interni) alla costante

```javascript
MYOBJ = {
  name: "Aldo",
  surname: "Rossi",
  age: 33,
};
```

## Ambito variabile

L'ambito in JavaScript si riferisce al contesto attuale del codice, che determina l'accessibilità delle variabili.  
Esistono tre diversi livelli di scope:  
globale, di funzione, di blocco.

### Ambito globale:

una variabile con ambito globale è accessibile da qualsiasi posizione all'interno dello script
da cui è stata creata. Viene dichiarato al livello più alto ed è accessibile dagli ambiti funzione e blocco.

### Ambito a livello di funzione:

è limitato all'interno della funzione in cui è stata dichiarata e qualsiasi ambito secondario
come le funzioni o le istruzioni annidate. Le variabili con scope a livello di funzione non sono accessibili al di fuori
della funzione in cui sono dichiarate.

### Ambito a livello di blocco:

è limitato ulteriormente alla dichiarazione o all'espressione in cui è stata dichiarata
la variabile, in pratica ovunque tra parentesi graffe.

In sintesi:  
var: ambito globale e/o a livello di funzione  
let e const: ambito globale e/o a livello di blocco

```javascript
//Ambito globale
var myGlobalVar = "var globale";
let myGlobalLet = "let globale";
const MYGLOBALCONST = "const globale";

function myFunction() {
  // Ambito funzione
  var myLocalVarF = "var locale funzione";
  let myLocalLetF = "let locale funzione";
  const MYLOCALCONSTF = "const locale funzione";

  // Accesso ad ambito globale
  // da ambito  funzione
  console.log(myGlobalVar); //accesso a Var globale da ambito  funzione
  console.log(myGlobalLet); //accesso a Let globale da ambito  funzione
  console.log(MYGLOBALCONST); //accesso a Const globale da ambito  funzione

  if (true) {
    // Ambito  blocco
    var myLocalVarB = "var locale blocco";
    let myLocalLetB = "let locale blocco";
    const MYLOCALCONSTB = "const locale blocco";

    // Accesso ad ambito  funzione
    // da ambito  blocco
    console.log(myLocalVarF); //accesso a Var esterna ambito  blocco
    console.log(myLocalLetF); //accesso a Let esterna all'ambito  blocco
    console.log(MYLOCALCONSTF); //accesso a Const esterna all'ambito  blocco
  }

  // Accesso ad ambito  blocco
  // da ambito  funzione

  // OK: var è visibile fuori dall'ambito blocco
  console.log(myLocalVarB); //accesso a Var di blocco da ambito funzione

  // Errore: let non è visibile fuori dall'ambito blocco
  console.log(myLocalLetB); //accesso a Let di blocco da ambito funzione

  // Errore: const non è visibile fuori dall'ambito blocco
  console.log(MYLOCALCONSTB); //accesso a Const di blocco da ambito funzione
}

// Errore: nulla è visibile fuori dagli ambiti funzione e blocco
console.log(myLocalVarF); // Var funzione da ambito globale
console.log(myLocalVarB); // Var blocco da ambito globale
console.log(myLocalLetF); //Let funzione da ambito globale
console.log(myLocalLetB); //Let blocco da ambito globale
console.log(MYLOCALCONSTF); //Const funzione da ambito globale
console.log(MYLOCALCONSTB); //Const blocco da ambito globale

// Chiama la funzione
myFunction();
```
