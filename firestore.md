# Firestore

[How to Structure Your Data](https://www.youtube.com/watch?v=haMOUb3KVSo)
[Write Information](https://angularfirebase.com/lessons/firestore-nosql-data-modeling-by-example/)

## Regole

1. Documents have a limits - Documenti hanno un limite di lunghezza
2. You can't retrive partial document - Non puoi ritornare da query documenti parziali
3. Queries are shallow - Le quey sono lente
4. You are billed by the number of reads and writes you perform - Spendi soldi in base a quante letture e scritture fai
5. Query find document in collections - Le query cercano solo in una collezione di documenti
6. Array are weird - Gli array sono strani (altre traduzioni?)

## Esempio Pratico

Abbiamo una serie di ristoranti

### Simple Restaurant Collection

App: Pagina Lista Ristoranti -> Pagina Dettaglio Ristorantea

| Restaurant | nome | rating |

### Restaurant and Review 

E le review? In una collezione dentro ad ogni documento. Path: /restaurant/<IdRestaurant>/review/<IdReview>

| Restaurant | nome | rating | _review_ |
- | Review | userId | rating | text | 


#### Review Problem

E se l'utente navigandando torna avanti e indietro dalla _pagina lista ristoranti_ alla _pagina dettaglio ristorante_?
- Scarichiamo ogni volta tutte le review del suddetto ristorante?... Per ora si, non so come sincronizzare i dati

