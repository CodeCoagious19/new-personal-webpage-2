---
title: "07 - Esercitazione. Conta parole"
excerpt: "Javascript"
permalink: /javascript-modulo-base/07-js-modulo-base
last_modified_at: 2021-01-10
---

## Conta parole

Il seguente esempio conta le parole inserite in un certo input testuale.
Faremo uso dell'evento `keypress` che scatta ad ogni tasto premuto e del metodo su stringa `split()`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

    <h1>Conta parole</h1>

    <table>
        <td>Testo:</td>
        <tr>
            <td><textarea cols="30" rows="10" id="myText" ></textarea></td>
        </tr>
        <tr>
            <td>Parole nel testo:</td>
        </tr>
        <tr>
            <td><input type="text" id="word-count"></td>
        </tr>    
    </table>

    <!-- Collegamento alla libreria JQuery.--> 
    <script type="text/javascript" src="jquery-3.5.1.min.js"></script>

    <script>        
        function contaParole(){
            //Prelievo il valore dell'elemento con id="myText" lo converto a stringa e lo assegno alla variabile testoInserito
            let testoInserito = String($("#myText").val()); 
            //Prelievo la proprietà lenght di un array formato da parole separate da spazi.
            //ATTENZIONE. NON FUNZIONA CON I DOPPI SPAZI
            let conteggioParole = (testoInserito.split(" ").length);
            $("#word-count").val(conteggioParole)
        }

        $( function(){ 
            $("#myText").keypress(contaParole)
        });
    </script>
</body>
</html>
```

![](./images/lezione06es1.gif)



