## Codice Javascript

posso scrivere il codice javascript ell'heand del file html direttemante tra i tag

```html
<script></script>
```

oppure sempre nell'head carico il file js fornendolo nell'attributo src dello stesso tag:

```html
<script src="myjavascript.js"></script>
```

Il tag `<script>` può anche essere messo prima della chiusura del body scrivendo il codice direttamente
oppure caricando il file con l'attributo src

## Metodi Builtin

Sono funzioni fornite dal linguaggio per eseguire operazioni comuni
Il metodo alert(), ad esempio, apre una finestra di avviso contenente il testo definito tra parentesi

```javascript
window.alert("Questo è l'alert");
```

## Funzioni Custom

Per dichiarare una funzione occorre utilizzare la parola chiave function seguita
dal nome della funzione e dal corpo della funzione tra parentesi graffe

```javascript
function scriviSomma() {
  let a = 10;
  const b = 4;
  const risultato = a + b;
  console.log(risultato);
}
```

## Funzioni con parametri

Una funzione può anche utilizzare variabili in forma di parametri.
Questi vengono racchiusi nella parentesi tonda della funzione e separati da una virgola.

```javascript
function scriviSommaParametri(a, b) {
  const risultato = a + b;
  window.alert(risultato);
}
```

Nel seguente codice ho tre button. I metodi `scriviSomma()` e `scriviSommaParametri()` vengono eseguiti
all'evento `onclick` sui rispettivi button

```html
<body>
  <button onclick="scriviSomma()">Chiama funzione</button>
  <button onclick="scriviSommaParametri(12, 5)">Chiama funzione con par</button>
  <button onclick="eseguiCodiceEsterno()">
    Chiama funzione da file esterno
  </button>
</body>
```

Es. scrivo il codice all'interno del tag script prima della chiusura del body

```html
<script>
  alert("Ciao");

  let x = 1,
    y = 0;

  while (x < 100) {
    x++;
    y = x + 1;
    if (x == 99) {
      break;
    }
  }
  console.log(x, y);
</script>
```
