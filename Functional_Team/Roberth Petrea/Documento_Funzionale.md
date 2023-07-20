
# Documento Funzionale
Per l’integrazione del sistema nella piattaforma Salesforce è richiesta la presenza di 7 object:

## Account
Oggetto standard sulla piattaforma, relativo ai clienti. I field da inserire all’interno dell’oggeto verranno riferiti non appena giungeranno informazioni dal cliente.
Per il momento si suppongono necessari Dati anagrafici (nome, cognome, emailanno di nascita, residenza), punto vendita di appartenenza (picklist le cui scelte sono Punto Vendita 1, Punto Vendita 2,...)  
Ciascun record dovrà contenere una related list dove si potrà visualizzare le opportunity associate.
### Template
Al momento della registrazione il cliente dovrà ricevere un’email riguardante il successo dell’operazione. Va quindi creato un e-mail template contenente il seguente body:  

“Caro {!Account.Name},  
La tua registrazione è stata correttamente effettuata!  
Cordiali Saluti,  
Il team di Lacoste”.  

Una volta che il cliente verrà registrato dovrà quindi ricevere l’email di conferma tramite logica flow. La logica sarà che al momento della creazione del record relativo all'oggetto "Account", verrà recapitata un'email, utilizzando il template, all'indirizzo specificato nell'account stesso.

## Lead 
Oggetto standard sulla piattaforma, relativo ai clienti la cui e-mail non è stata ancora confermata. Non appena giungeranno le informazioni dal cliente verranno specificati di seguito i fields che tale oggetto dovrà contenere;
per il momento inserire gli stessi field relativi all’oggetto Account.  
La registrazione deve poter avvenire anche tramite sito web dell'azienda, va dunque implementata tramite Web-to-Lead selezionando come "selected fields" tutti i campi disponibili.

## Opportunity
Oggetto standard nella piattaforma, relativo alle vendite. I field che deve contenere si presume siano Incasso, Data di Conclusione, Venditore, Cliente (account), stato dell’ordine (Ordine effettuato, In Consegna, Consegnato).
Gli altri field verranno aggiunti una volta ricevute le informazioni da parte del cliente.
Questo oggetto dovrà inoltre contenere al suo interno un Path relativo allo stato dell’ordine, dunque, conterrà i medesimi stati (Ordine Effettuato, In Consegna, Consegnato). 
Non sono state fornite informazioni riguardanti i field da mostrare per ciascuno stato, quindi non inserirne alcuno.
All'interno della pagina relativa ad un record, dovrà essere presente una related list dove sarà possibile visualizzare gli oggetti prodotto che sono stati venduti all'interno del record stesso.

## Prodotto
Oggetto standard, relativo al prodotto, deve contenere tipologia di prodotto (picklist: T-shirt, Polo, Pants, Shoes, Jacket, Socks, Dress, Hat, Skirt, Bag), Prezzo. Gli altri field verranno aggiunti una volta ricevute le informazioni da parte del cliente.

## Venditore
Oggetto custom, relativo ai venditori, i field che deve contenere sono i dati anagrafici del venditore (nome, cognome, anno di nascita, email), punto vendita di appartenenza. Gli altri field verranno aggiunti una volta ricevute le informazioni da parte del cliente.

## Magazzino
Oggetto custom, relativo al magazzino; Si presume che debba contenere il field relativo alla quantità presente in magazzino di ciascuna tipologia di prodotto. Deve esserci anche il field relativo al punto vendita associato al magazzino.
Gli altri field verranno aggiunti una volta ricevute le informazioni da parte del cliente.

## Punto Vendita
Oggetto custom contenente le informazioni dei punti vendita:
* Nome
* Regione
* Provincia
  
