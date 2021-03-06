---
title: "14 - Operatori Logici e logica booleana"
excerpt: "Javascript"
permalink: /javascript-modulo-base/14-js-modulo-base
last_modified_at: 2021-01-10
---


## Operatori Logici

Gli operatori logici `<`, `<=`, `==`, `>`, `>=`, `!=` ..  trattano l'espressione come un espressione logica e ritornano un valore booleano. Sono spesso utilizzati nel controllo di condizioni in costruttti `if` o cicli `while`, `for` e tutti i costrutti condizionali e iterativi inerenti.  

```js
console.log(1 >= 5);           //false
//Per le stringhe si segue un ordine lessicografico
console.log("ciao" < "pasta"); //true
console.log(12 != 5); /        //true
```

**Nota - Operatore di uguaglianza:** == Vs ===

Entrambi sono operatori logici di uguaglianza.

- `===`: **Uguaglianza forte**, valuta l'uguaglianza dell'espressione valutanto il tipo e il contenuto.
- `==`: **Uguaglianza debole**, valuta l'uguaglianza dell'espressione valutanto il contenuto effettuando prima una conversione di tipo.


```js
/* === */
console.log(5 === 5);            //true
console.log(15 === "15");        //false -> sono tipi di dati diversi, il primo è un numero, il secondo è una stringa
console.log(null === undefined); //false -> sono tipi di dati diversi.

/* == */
console.log(5 == 5);             //true
console.log(15 == "15");         //true!! -> sono tipi di dati diversi, il primo è un numero, il secondo è una stringa ma il contenuto è lo stesso

console.log(false == 0);         //true!! -> entrambi hanno un valore falsy anche se il tipo è diverso
console.log(null == undefined);  //true!! -> entrambi hanno un valore falsy anche se il tipo è diverso
```

In generale l'uguaglianza forte è da preferire per essere sicuri di effettuare quindi anche un controllo sul tipo e rendere più semplice l'individuazione di errori run-time spesso causati da conversioni implicite di Javascript.

## Logica Booleana

Trattano l'espressione come un'espressione logica e permettono la concatenazione di espressioni con più operatori logici. Ritornano un valore booleano: `TRUE`, `FALSE`.
Vediamo i principali:

**AND** : `condition1 && condition2`: Ritorna *true* se entrambe `condition1` e `condition2` risultano *true*. <br>
**OR**  : `condition1 || condition2`: Ritorna *true* se almeno una tra `condition1` e `condition2` risulta *true*. <br>
**NOT** : `!condition1`: Inverte il risultato logico di `condition1`. <br>


```js
console.log( (1 >= 5) || ("ciao" < "pasta") );  //true
console.log( ("ciao" < "pasta") && (12 == 5) ); //false
```

## Approfondimento - Short evalutation

Se un' espressione logica risulta necessariamente *true* o *false* le elaborazioni concatenate non vengono elaborate.

- `true || expr`: `expr` non viene valutata
- `false && expr`: `expr` non viene valutata

Esempio:
```js
console.log( (1 < 2) || ("ciao" < "pasta") ); //true,  ("ciao" < "pasta") non viene valutata
console.log( (12 == 5) && ("c" < "p") ); //false, ("c" < "p") non viene valutata
```

## Truthy e falsy

I valori `truthy` e `falsy` sono quei valori considerati rispettivamente sempre veri o falsi o per meglio dire che ritornano sempre un boolean: *true/false*.

- Valori truthy: `1`, `"content"` ..
- Valori falsy: `undefined`, `null`, `0`, `""`, `NaN`

Vedremo adesso come mettere in pratica questi concetti attraverso l'uso di costrutti condizionali e iterativi.



  


