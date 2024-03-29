# Soluzione migliore per collaborare

Tutto quanto verrà aggiornato man mano.
Date inizialmente un'occhiata ai termini a fine pagina per una maggiore comprensione del testo.

Mi scuso per il linguaggio molto grezzo. E' per essere veloce e chiaro e in brevi termini, buona lettura.

## Una piccola introduzione

1. La app funziona a screen. Ogni screen ha delle proprietà uniche:
    - Una sola AppBar o una sola [SliverAppBar](https://www.youtube.com/watch?v=R9C5KMJKluE&t=2s)
    - Al massimo due drawer, uno a sinistra e uno a destra. (Il drawer di sinistra sostituisce il backButton)
    - Una sola BottomBar
2. In uno screen ci possono essere più page. Le page sono gestite da:
    - BottomBar: minimo 2, massimo 5
    - TabBar: minimo 2, massimo infinito. Le view della TabBar non devono contenere nessuna proprietà degli screen

## Regole per Aiutare il Programmatore

Non sono in ordine di importanza.

1. Tutti i testi con le medesime funzioni dovrebbero avere lo stesso style.
    - Se necessario si può cambiare style ma dando un senso. Mi spiego:
        - Tutti i prezzi degli alimenti in rosso, tutti i prezzi dei drink, in verde. Non deve cambiare il colore per schermata ma per significato che acquisisce il prezzo per dare meno confusione anche a chi usa l'app.
    - Esempio: Il prezzo dei prodotti nelle varie schermate dovrà essere sempre rosso e sottolineato. Non dovrebbero cambiare in ogni schermata.
    - Esempio: I titoli dei paragrafi devono essere in grassetto e in verde. Non dovrebbero cambiare ad ogni schermata
2. Seguire le line guida del [Material Design](https://material.io/). Flutter è basato su questo style
3. La BottomBar è utilizzata per la Navigazione per ciò le view che utilizzerà dovranno avere un'interazione di Navigazione
    - Esempio: BottomBar(ristorante, menu, promozioni). Permetteno di visulizzare le varie informazioni, _va bene_
    - Esempio: BottomBar(ristorante, menu, recensisci). 'recensisci' non è una view di Navigazio ma di input. Non va bene. Crea confusione a chi usa l'app e complica la gestione e creazione di essa.
4. La TabBar, ha solo la funzione di scorrimento delle view, lasciategli questa funzione e basta.
5. Il Drawer non è permanente in ogni screen, si potrebbe fare ma è meglio evitare. Se necessaria una funzione del genere usate la BottomBar.
6. Flutter usa dei themi prestabiliti per il testo, consulta [TextTheme](https://docs.flutter.io/flutter/material/TextTheme-class.html) nella seconda tabella.
    - [Lista font](https://fonts.google.com/)
    I temi 'displayX' sono consogliati per essere molto costumizzabili. Sottolineatura, grassetto, dimensioni ecc...
    Cercate di dare un significato a ogni thema.
    - Esempio: 'title' usatelo per i titoli dei ristornati
    - Esempio: 'subTitle' usatelo per i titoli dei paragrafi
    - Esempio: 'caption' per tutto ciò che è un postscriptum ad esempio
    - Esempio: 'display1' con fontsize 12 e in grasetto e in rosso per il prezzo
7. Per i colori vedi [Color Theme Creation](https://material.io/design/color/#color-theme-creation)
    - Nell'ultima versione d Flutter si preferisce: (in [ColorScheme](https://docs.flutter.io/flutter/material/ColorScheme-class.html))
        - **primary**: Rappresenta il colore primario dell'app, si ritrova nella AppBar per esempio
        - **primaryVariation: ...
        - **secondary**: Rappresenta il colore secondario, si ritrova nei bottoni, nella TabBar, nei Switch ecc...
        - **error**: Rappresenta il colore che segnala un errore
    - Nelle verisione più vecchie:
        - un colore primario _prymarySwatch / primaryColor_
        - un colore per bottoni _buttonColor_
        - un colore per evidenziazioni _accentColor_ (Esempio, arrivato a fine pagina/fine scrolling)
        - un colore per errori _errorColor_
    - Servono altri colori? Non saremmo più in stile Material Design, possiamo fare questo strappo alla regola ma preferiamo di no se è possibile    

## Richieste se potete

1. Create un diagramma di flusso prima di creare l'app.
    - Rettangoli: rappresentano una View
    - Rombi: Rappresentano una scelta un bottone.
    Perchè è utile? Per voi per progettare al meglio la UserExperience, per capire a colpo d'occhio dove si sta creando confusione o ripetendo pulsanti o funzioni e al programmatore per creare la Basi di Dati(Database) o per capire cose si può e non può fare.
    Non va snelizzato. Anzi qualsiasi cosa il cliente vorrebbe va disegnata.
<p align="center">
  <img src="/images/flowchart.png" width="350" alt="accessibility text">
    Un Esempio molto semplice ma sbagliato. Per farvi capire.
</p>

2. Dare un significato sensato alle img
3. Le uniche immagini necessarie sono quelle di copertina e per la Demo di una sola dimensione, la più grande.
    Facciamo un esempio. Le img delle icone, sono inutili, utilizzate le icone definite in precedenza, le immagini dei bottoni pure, vengono ricreati a livello di codice. Le img che fanno da copertina sono quelle utili, img del ristorante, img del piatto, img delle tipologie, ecc..

## Informazioni esterne

Abbiatene cura.

### Icone

Per le icone consultare [Flutter Icon](http://fluttericon.com/).

- Le icone integrabili senza problemi sono:
  - Material Desing Icon
  - Font Awesome
- Per le altre icone chiedere al programmatore
- Per aggiungere nuove icon crearne di nuove in formato svg(Grafica vettoriale, svg icon/font) tramite per esempio [Adobe Illustrator](https://www.adobe.com/it/products/illustrator.html)
    - Il programmatore una volta ricevuto il file svg andrà su Flutter Icon e si dorvà trascinare l'icona
    - _Ancora da provare_

_Perchè non utilizzare le immagini al posto delle icone?_
    - Le immagini non si adattano in modo automatico alla risoluzione del dispositivo
    - Le immagini occupano maggior spazio, per ciò maggior appesantezza di download dallo store dell'app
    - Le immagini sono qualitivamente inferiori ad una icona

### User Interface

- [Flutter Awesome](https://github.com/Solido/awesome-flutter/blob/master/README.md): Una raccolta di grafiche e di molto altro!
- [2Dimension](https://www.2dimensions.com/about-flare): Per animare icone e molto altro!
- [It's All Widgets](https://itsallwidgets.com/): Una raccolta di app per poter prendere spunto e anche i Widget! (Selezionare OpenSource)

## Termini

- **img**: Immagini
- **Widget**: Tutto ciò che si vede a schermo, un testo, un'icona, un'immagine, un layout(a colonna, a riga, a griglia), le barre in alto in basso, tutto.
- **View**: Un'insieme di Widget che rappresentano un'interfaccia utente o una pagina con un significato ben preciso. 
- **Page**: Identifica una view associata a un bottone di un BottomBar per esempio.
- **screen**: Schermata dell'app.

- **AppBar**: La barra in alto che contiene il titolo e la azione, il drawer e il button di back(indietro).
- [**SliverAppBar**](https://www.youtube.com/watch?v=R9C5KMJKluE&t=2s): AppBar più elegante e moderna con generalmente un'immagine di sfondo
- **BackButton**: Bottone che si trova all'inizio dell'AppBar, permette di tornare al screen precedente.
- **Drawer**: Il menu Laterale a sinistra o a destra.
- **BottomBar**: La barra in basso per la navigazione in modo istantaneo.
- **TabBar**: La barra che permette di naviagare tra le TabView si trova generalmente sopra quest'ultime.

<p align="center">
  <img src="/images/screen1.jpg" width="350" title="hover text">
  <img src="/images/screen2.jpg" width="350" alt="accessibility text">
</p>
