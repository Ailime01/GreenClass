
# Documento Funzionale
Per l’integrazione del sistema nella piattaforma Salesforce è richiesta la presenza di 6 object:

## Account
Oggetto standard sulla piattaforma, relativo ai clienti. I field da inserire all’interno dell’oggetti verranno riferiti non appena giungeranno informazioni dal cliente.
Per il momento si suppongono necessari Dati anagrafici (nome, cognome, emailanno di nascita, residenza). Al momento della registrazione il cliente dovrà ricevere un’email riguardante il successo dell’operazione. Va quindi creato un e-mail template contenente il seguente body:
### Template
“Caro {!Account.OwnerFullName}, 
La tua registrazione è stata correttamente effettuata!
Cordiali Saluti,
Il team di Lacoste”.
Una volta che il cliente verrà registrato dovrà quindi ricevere l’email di conferma tramite logica flow.

## Lead 
Oggetto standard sulla piattaforma, relativo ai clienti la cui e-mail non è stata ancora confermata. Non appena giungeranno le informazioni dal cliente verranno specificati di seguito i fields che tale oggetto dovrà contenere;
per il momento inserire gli stessi field relativi all’oggetto Account. 

## Opportunity
Oggetto standard nella piattaforma, relativo alle vendite. I field che deve contenere si presume siano Incasso, Data di Conclusione, Venditore, Cliente (account), stato dell’ordine (Ordine effettuato, In Consegna, Consegnato).
Gli altri field verranno aggiunti una volta ricevute le informazioni da parte del cliente.
Questo oggetto dovrà inoltre contenere al suo interno un Path relativo allo stato dell’ordine, dunque, conterrà i medesimi stati (Ordine Effettuato, In Consegna, Consegnato). 
Non sono state fornite informazioni riguardanti i field da mostrare per ciascuno stato, quindi non inserirne alcuno.

## Prodotto
Oggetto standard, relativo al prodotto, deve contenere Nome prodotto, Prezzo. Gli altri field verranno aggiunti una volta ricevute le informazioni da parte del cliente.

## Venditore
Oggetto custom, relativo ai venditori, i field che deve contenere sono i dati anagrafici del venditore (nome, cognome, anno di nascita, email), punto vendita di appartenenza. Gli altri field verranno aggiunti una volta ricevute le informazioni da parte del cliente.

## Magazzino
Oggetto custom, relativo al magazzino; Si presume che debba contenere il field relativo alla quantità presente in magazzino di ciascuna tipologia di prodotto.
Gli altri field verranno aggiunti una volta ricevute le informazioni da parte del cliente.
