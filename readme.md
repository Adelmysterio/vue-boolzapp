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