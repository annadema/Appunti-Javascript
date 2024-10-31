### Array

Serie di elementi (valori o oggetti) definiti da indice:valore

```javascript
let myArray = new Array();
```

Array di lunghezza definita ma dinamica

```javascript
let myArray2 = new Array(5);
```

Array con più di un argomento, dichiara i valori dell'array

```javascript
let myArray3 = new Array("Aldo", "Giovanni", "Giacomo");
```

In un letterale array possono essere inclusi degli elementi non definiti

```javascript
const myArray4 = [1, , , 4];
console.log("elementi: " + myArray4);
```

Sintassi con interpolazione

```javascript
console.log(`elementi: ${myArray4}`);
```

La proprietà length ritorna il numero di elementi presenti nell'array

```javascript
console.log(`lunghezza ${myArray3.length} elementi: ${myArray3}`);
```

### Sintassi per l'iterazione degli array

### For classico

```javascript
for (let i = 0; i < myArray3.length; i++) {
  console.log(`For-classico - myArray 3 contiene: ${myArray3[i]}.`);
}
```

### For-in:

sintassi alternativa che lavora sugli indici dell'array

```javascript
for (let indice in myArray3) {
  console.log(`For-in - myArray 3 contiene: ${indice} : ${myArray3[indice]}`);
}
```

### For-of:

sintassi alternativa che lavora sui valori dell'array

```javascript
for (let valore of myArray3) {
  console.log(`For-of - myArray 3 contiene: ${valore}`);
}
```

### Modifica length

```javascript
myArray3.length = 2;
console.log(
  `myArray 3 contiene i seguenti ${myArray3.length} elementi: ${myArray3}`
);
for (let i in myArray3) {
  console.log(`Lengh modificato - myArray 3 contiene: ${myArray3}`);
}
```

### Push e Pop

aggiungono e eliminano in coda

```javascript
myArray3.push("Ajeje");
for (let i in myArray3) {
  console.log(`Push - myArray 3 contiene: ${myArray3}`);
}
myArray3.pop();
for (let i in myArray3) {
  console.log(`Pop - myArray 3 contiene: ${myArray3}`);
}
```

### Unshift e Shift

aggiungono e eliminano in testa

```javascript
myArray3.unshift("Pino");
for (let i in myArray3) {
  console.log(`Unshift - myArray 3 contiene: ${myArray3}`);
}
myArray3.shift();
console.log(`Shift - myArray 3 contiene: ${myArray3}`);
```

### Splice sostituisce dall'elemento n, n elementi con nuovo/i elemento/i

```javascript
myArray3.splice(0, 2, "A", "B", "C", "D");
console.log(`Splice - myArray 3 contiene: ${myArray3}`);
```

### Slice taglia da elemento a elemento

```javascript
let myArraySliced = myArray3.slice(0, 3);
console.log(`Slice - myArray sliced contiene: ${myArraySliced}`);
```

### Concat

```javascript
let myArrayConcat = myArray3.concat(myArraySliced).concat("Z", "Y", "X");
console.log(`Concat - myArrayConcat contiene: ${myArrayConcat}`);
```

### Sort e revert

console.log(`Sort - myArraySorted contiene: ${myArrayConcat.sort()}`);
console.log(`Reverse - myArray Reversed contiene: ${myArrayConcat.reverse()}`);

### Join

converte array in stringa con eventuale nuovo separatore

```javascript
console.log(`Join - Stringa ottenuta da array: ${myArrayConcat.join(",")}`);
```

### map()

passa alla funzione specificata ogni elemento dell’array e restituisce un array contenente i valori restituiti dalla funzione

```javascript
let myArrayNumbers = [1, 2, 3, 4, 5, 6, 7, 8];
let myMappedArray = myArrayNumbers.map((elemento) => elemento / 33);

let myMappedArray2 = new Array();
for (let indice in myArrayNumbers) {
  myMappedArray2[indice] = myArrayNumbers[indice] / 33;
}

console.log(myMappedArray);
console.log(myMappedArray2);

let myArrayNames = ["a", "b", "c"];
console.log(myArrayNames);
let myMappedArrayNames = myArrayNames.map((elemento) =>
  elemento.toLocaleUpperCase()
);
console.log(myMappedArrayNames);
```

### filter()

restituisce un array contenente un sottoinsieme dell’array sorgente

```javascript
let myFilteredArray = myArrayNumbers.filter((e) => e % 2 === 0);
console.log("Filter: " + myFilteredArray);
```

### find() e findIndex()

restituiscono rispettivamente il valore in base all'indice e l'indice in base al valore

```javascript
console.log("Find: " + myArrayNumbers.find((e) => e === 2));
console.log("FindIndex: " + myArrayNumbers.findIndex((e) => e === 2));
```

### every() e some()

restituiscono booleano se tutti (every) o almeno uno (some) elemento risponde alla condizione

```javascript
let myArrayBlended = [0, 1, 2, "A", "B", "C"];
console.log("Every: " + myArrayBlended.every((e) => typeof e === "number"));
console.log("Some: " + myArrayBlended.some((e) => typeof e === "number"));
```

### reduce()

combina gli elementi di un array, per produrre un singolo valore

```javascript
let myReducedArray = myArrayNumbers.reduce((x = 3, y) => {
  console.log(x + " - " + y);
  Math.pow(x, y);
});
console.log("Reduce: " + myReducedArray);
```

### flat()

crea un nuovo array con gli stessi elementi dell’array su cui è stato richiamato  
se gli elementi sono array vengono “appiattiti”

```javascript
let myNestedArray = [
  [1, 2, 3, ["A", "B", "C"]],
  [4, 5, 6],
  [7, 8, 9],
];
```

L'argomento indica il livello di annidamento da raggiungere

```javascript
let myFlattedArray = myNestedArray.flat(3);
for (let e of myNestedArray) {
  console.log("Nested: " + e);
}
for (let e of myFlattedArray) {
  console.log("Flat: " + e);
}
```

### flatMap()

unisce map() e flat(1)

```javascript
let myPhrasesArray = ["Hello world", "How are you?"];
let myWordsArray = myPhrasesArray.flatMap((e) => e.split(" "));
console.log("FlatMap: " + myWordsArray);
```

### indexOf() e lastIndexOf()

cercano (dall'inizio o dalla fine) un elemento avente il valore specificato e restituiscono l’indice del primo elemento trovato

```javascript
console.log("IndexOf: " + myArrayNumbers.indexOf(1));
console.log("LastIndexOf: " + myArrayNumbers.lastIndexOf(1));
```

### sort()

restituisce l’array ordinato in ordine ascendente

```javascript
console.log("Sort: " + myArrayNumbers.sort());
```

Per ordinare un array in un ordine diverso da quello alfabetico, occorre passare una funzione di confronto come argomento

```javascript
console.log("Sort custom: " + myArrayNumbers.sort((a, z) => z - a));
```

### reverse()

restituisce l’array con ordine inverso

```javascript
myArrayNumbers = [1, 2, 3, 4, 5, 1];
console.log("Reverse: " + myArrayNumbers.reverse());
```

### join()

converte tutti gli elementi di un array in stringhe e li concatena

```javascript
console.log("Join: " + myArrayNumbers.join(" # "));
```

### String.split()

crea un array da una stringa

```javascript
let myString = "Aldo,Giovanni,Giacomo";
console.log("Stringa: " + myString);
let mySplitted = myString.split(",");
for (e of mySplitted) {
  console.log("Split: " + e);
}
```
