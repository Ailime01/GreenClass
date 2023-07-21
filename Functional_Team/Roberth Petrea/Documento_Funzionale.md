
# Documento Funzionale
Per l’integrazione del sistema nella piattaforma Salesforce è richiesta la presenza di 6 object:

## Account
Oggetto standard sulla piattaforma, relativo ai clienti. I field da inserire all’interno dell’oggeto verranno riferiti non appena giungeranno informazioni dal cliente.  
Campi: 
* Nome
* Cognome
* Numero Tessera
* Email
* Prodotto acquistato
* Punto vendita di appartenenza (picklist le cui scelte sono Punto Vendita 1, Punto Vendita 2,...)
  
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
Oggetto standard nella piattaforma, relativo alle vendite. I field che deve contenere si presume siano:
* Incasso,
* Data di Conclusione
* Venditore
* Cliente (account)
* Stato dell’ordine (Ordine effettuato, In Consegna, Consegnato).
  
Gli altri field verranno aggiunti una volta ricevute le informazioni da parte del cliente.
Questo oggetto dovrà inoltre contenere al suo interno un Path relativo allo stato dell’ordine, dunque, conterrà i medesimi stati (Ordine Effettuato, In Consegna, Consegnato). 
Non sono state fornite informazioni riguardanti i field da mostrare per ciascuno stato, quindi non inserirne alcuno.
All'interno della pagina relativa ad un record, dovrà essere presente una related list dove sarà possibile visualizzare gli oggetti prodotto che sono stati venduti all'interno del record stesso.

## Product
Oggetto standard, relativo al prodotto, deve contenere:
* Tipologia di prodotto (picklist: T-shirt, Polo, Pants, Shoes, Jacket, Socks, Dress, Hat, Skirt, Bag)
* Prezzo
* Quantità di prodotto  

## Seller
Oggetto custom, relativo ai venditori, i field che deve contenere sono:
* Nome
* Cognome
* Matricola
* Email
* Telefono
* Prodotto venduto
* Punto vendita di appartenenza.
* Ranking nello store
* Ranking vendite globale

## Sales Point
Oggetto custom contenente le informazioni dei punti vendita:
* Nome
* Regione
* Provincia
  
