---
title: "13 - Precedenza e associatività degli operatori"
excerpt: "Javascript"
permalink: /javascript-modulo-base/13-js-modulo-base
last_modified_at: 2021-01-10
---

## Operator Precedence

La precedenza degli operatori determina la priorità in cui gli operatori vengono valutati. Gli operatori con precedenza più alta sono valutati prima degli operatori con precedenza più bassa.

La lista completa di tutti gli operatori con le rispettive precedenze la troviamo qua: 
[MDN - Operator Precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

Da notare che l'operatore `( )` ha la priorità più alta e quindi la precedenza su tutti gli operatori. Questo significa che per forzare la precedenza, esattamente come per la matematica è possibile sfruttare le parentesi `( )`.

**Regola di buona programmazione:** Non è mai una buona pratica di programmazione lasciare espressioni troppo complesse prive di parentesi anche se sono rispettate dal punto di vista semantico tutte le precedenze previste. Le parentesi, oltre a forzare la precedenza, offrono visivamente una chiarezza maggiore, evitando di commettere errori banali di svista.

```js
/* Operatore precedence */
/* Calcolo eta' media */

const questAnno = 2020;
const maggiorenne = 18;

const nascitaMarco = 1996;
const nascitaLuca = 2006;


/* l'operatore "-" ha precedenza sull'operatore ">" quindi l'espressione è svolta correttamente da sinistra verso destra
La sottrazione verrà quindi svolta prima dell'operatore ">" */
let isMaggiorenne = questAnno - nascitaMarco > maggiorenne
console.log(isMaggiorenne); //true
let isMaggiorenne = questAnno - nascitaMarco > maggiorenne
console.log(isMaggiorenne); //false

//Grouping
const etaMarco = questAnno - nascitaMarco; //24
const etaLuca = questAnno - nascitaLuca;   //14

// In questo caso poichè la divisione ha precedenza sulla somma è necessario forzare la priorità inserendo le parentesi
// Calcolo età media
console.log ( (etaMarco + nascitaLuca)/2 ); //19
```

## Associatività

L'associatività specifica in che modo vengono eseguite le elaborazioni a parità di operatore.
Mentre la precedenza valuta la priorità, l'associatività valuta la modalità di esecuzione. Quasi tutti gli operatori hanno un'associatività *left-to-right* ovvero, l'elaborazione è da sinistra verso destra esattamente come per la matematica. 

Alla pagina [MDN - Operator Precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) si trova una tabella riassuntiva che mostra priorità/associatività per ogni operatore.


```js
//Associatività del'operatore +. L'operatore + vale sia da somma che da concatenazione stringa
for(let i=0, j=5; i<=j; i++,j--){
    document.writeln(i + j + " "); //5//5//5
}
for(let i=0, j=5; i<=j; i++,j--){
    document.writeln(i + (j + " ") ); //05//14//23
}
```

## Operatori di assegnamento

L'operatore di assegnazione semplice `=` viene utilizzato per assegnare un valore a una variabile. L'operazione di assegnazione restituisce il valore assegnato. È possibile concatenare l'operatore di assegnazione per assegnare un singolo valore a più variabili (multiple assignment).

```js
//Multiple assignement
// E' possibile dichiarare due variabili contemporaneamente
let x, y;

/*Molto importante! L'operatore "= è un operatore da destra a sinistra  */
x = y = (2 * 7) * 3 - 5; // 9 * 3 - 5 // 27 - 5 // 22

console.log(x); //22
console.log(y); //22
```

Molto utilizzati sono anche gli operatori di assegnamento composto come: `+=, -=, *=, /= ..` <br>

Hanno una sintassi molto chiara e compatta. Vengono utilizzati nei casi in cui è necessario elaborare anche il valore della variabile a sinistra contrariamente all'operatore di assegnamento semplice `=` che ignora e distrugge il valore contenuto a sinistra.

```js
let x = 10;

x *= 2; // x = x * 2
console.log(x); //20

x /= 2; // x = x / 2
console.log(x); //10
```


 

  
