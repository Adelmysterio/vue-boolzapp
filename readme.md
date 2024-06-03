<!-- Milestone 1
Replica della grafica con la possibilità di avere messaggi scritti dall’utente (verdi) e dall’interlocutore (bianco) assegnando due classi CSS diverse
Visualizzazione dinamica della lista contatti: tramite la direttiva v-for, visualizzare nome e immagine di ogni contatto -->

creo un metodo che cambi l estensione dei file avatar to jpg usando replace

invoco toJpg prima che il dom venga creato

collego gli elementi html ai diversi valori all interno del array usando v-for e v-bind

<!-- Milestone 2
Visualizzazione dinamica dei messaggi: tramite la direttiva v-for, visualizzare tutti i messaggi relativi al contatto attivo all’interno del pannello della conversazione
Click sul contatto mostra la conversazione del contatto cliccato -->

creo una variabile activeIndex = 0

creo un metodo changeActiveIndex con argomento i
    activeIndex = i

invoco la funzione su evento clink dei contatti

collego tramite v-bind la src del immagine e il nome del contatto al item all indice activeIndex

creo un ciclo v-for per i messaggi di contacts all indice activeindex

collego tramite v:bind il contenuto di dei messaggi e applico la classe sent se status == 'sent'

<!-- Milestone 3
Aggiunta di un messaggio: l’utente scrive un testo nella parte bassa e digitando “enter” il testo viene aggiunto al thread sopra, come messaggio verde
Risposta dall’interlocutore: ad ogni inserimento di un messaggio, l’utente riceverà un “ok” come risposta, che apparirà dopo 1 secondo. -->

creo una variabile newMessageContent = null

collego con v-model l input desiderato con newMessageContent

creo una varibile che mi stampi la data currentDateTime = new Date().toLocaleString()

creo un metodo updateDateTime per aggiornare la data ponendo currentDateTime = new Date().toLocaleString()

creo un metodo autoAnswer
    invoco updateDateTime
    dichiaro un oggetto newMessageTemp con chiavi
        date: this.currentDateTime,
        message: 'ok',
        status: 'received',
pusho newMessageTemp in this.contacts[i].messages

creo un metodo newMessage 
    invoco updateDateTime
    dichiaro un oggetto newMessageTemp con chiavi
        date: this.currentDateTime,
        message: this.newMessageContent,
        status: 'sent',
    se lunghezza di this.newMessageContent > 0 pusho newMessageTemp in this.contacts[i].messages e invoco autoAnswer in ritardo di 1000ms

invoco il metodo New Message al keyup.enter su inputdesiderato

<!-- Milestone 4
Ricerca utenti: scrivendo qualcosa nell’input a sinistra, vengono visualizzati solo i contatti il cui nome contiene le lettere inserite (es, Marco, Matteo Martina -> Scrivo “mar” rimangono solo Marco e Martina) -->

creo una variabile searchedName

collego tramite v-model sul input desiderato la variabile searchedName

creo un metodo searchName con argomento string
    faccio un ciclo for per leggere contacts
    if element include string allora element.visible = true 
    altrimenti element.visible = false

invoco la funzione searchName con argomento searchedName al keyup sul input desiderato

<!-- Milestone 5 - opzionale
Cancella messaggio: cliccando sul messaggio appare un menu a tendina che permette di cancellare il messaggio selezionato

Visualizzazione ora e ultimo messaggio inviato/ricevuto nella lista dei contatti  -->

<!-- cancella Messaggio -->
creo una varibile isDropdownShown = false

creo un metodo pushDropDown che mi inserisca isDropdownShown come chiave del oggetto messaggio per farlo creo un forEach su contact e al suo interno un foreach di messages ed aggiungo la chiave

invoco il metodo pushDropDown sul lifecycle hook created 

creo un metodo toggleDropdown che cambi il valore di isDropDownShown all interno di messages

creo un metodo deleteMessage che elimini il messaggio usando splice

creo il menu a tendina con html css e lo metto in display none

creo un bottone che quando cliccato mostri il menu a tendina all interno del v-for dei messaggi ed invoco toggleDropdown

creo un v-if usando isDropDownShown all interno degli item

invoco la funzione deleteMessaggio all interno del dropdown menu
