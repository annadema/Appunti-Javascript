# Espressioni

Un’espressione è un frammento di codice JavaScript che può essere valutato per restituire un valore.

### Espressioni semplici:

una costante, un nome di variabile

### Espressioni complesse:

costruite da più espressioni semplici.

Ad es. un’espressione di accesso a un array
è costituita da un’espressione che restituisce un array, seguita da una parentesi quadra aperta,
poi da un’espressione che restituisce un numero intero e infine da una parentesi quadra chiusa.

Un’espressione di chiamata di funzione è costituita da un’espressione che restituisce un oggetto funzione
e da zero o più espressioni aggiuntive che vengono utilizzate come argomenti della funzione.

Il modo più comune per creare un’espressione complessa partendo da espressioni più semplici è con un operatore.  
Un operatore combina in qualche modo i valori dei suoi operandi e restituisce un nuovo valore.  
Ad es.  
l’espressione `x * y` restituisce il prodotto dei valori delle due espressioni semplici x e y.

### Espressioni primarie:

non includono altre espressioni più semplici

```javascript
const myString = "Hello";
const myArray = ["Al", "John", "Jack"];
const myObj = { keyOne: "Value One", keyTwo: "Value Two" };
console.log(myString);
console.log(myArray);
console.log(myObj);
```

### Espressione di accesso alle proprietà di un oggetto o di un elemento di un array

JavaScript definisce due sintassi per l’accesso alle proprietà:

- espressione.identificatore (notazione a punto)
- espressione["espressione"] (notazione a parentesi)

```javascript
//Accesso alle proprietà di un oggetto
let person = {
  name: "Alice",
  age: 30,
};
console.log(person.name); // "Alice"
console.log(person.age); // 30
console.log(person["name"]); // "Alice"
console.log(person["age"]); // 30
//Accesso agli elementi di un array
let numbers = [1, 2, 3, 4, 5];
console.log(numbers[0]); // 1
console.log(numbers[2]); //3
const myObj2 = { "key One": "Value One" };
let myObj3;
console.log(myObj.keyOne); //Value One
console.log(myObj2["key One"]); //Value One
console.log(myObj3.someKey); //TypeError
```

Se il nome della proprietà include spazi o segni di punteggiatura oppure se è un numero (per gli array),
occorre necessariamente impiegare la notazione a parentesi.

Con entrambi i tipi di espressioni di accesso alle proprietà, viene valutata prima l’espressione che precede `. o [`

Se il suo valore è `null` o `undefined`, l’espressione lancia un **TypeError**, dal momento che non possono avere proprietà.

### Espressioni di accesso condizionale alla proprietà (ES2020):

- espressione?.identificatore
- espressione?.["espressione"]

```javascript
console.log(myObj3?.someKey); //undefined (no TypeError)
console.log(myObj3?.["someKey"]); //undefined (no TypeError)
```

### Espressione di definizione di una funzione

```javascript
const myFunc = function () {
  return "MyFunc body";
};
```

### Espressione di chiamata (esecuzione) di una funzione o di un metodo

```javascript
console.log(myFunc()); //MyFunc body
console.log(Math.sqrt(9)); //3
// Chiamata condizionale
let myFunc2;
console.log(myFunc2()); //TypeError
console.log(myFunc2?.()); //undefined
console.log(Math.method()); //TypeError
console.log(Math.method?.()); //undefined
```

### Espressione di creazione di un oggetto

Crea un nuovo oggetto e richiama una funzione (il costruttore) per inizializzare le proprietà dell’oggetto creato.
Se alla funzione costruttore di un oggetto non viene passato nessun argomento, la coppia di parentesi vuota può essere omessa:

```javascript
const myDate = new Date();
const myDate2 = new Date();
console.log(myDate);
console.log(myDate2);
```
