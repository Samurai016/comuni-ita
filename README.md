# [Comuni ITA API](https://samurai016.github.io/Comuni-ITA/)
![Versione](https://img.shields.io/badge/versione-v3.0.1-%23007ec6?style=flat-square)
[![Hosted on Supabase](https://img.shields.io/badge/Hosted%20on%20Supabase-passing?style=flat-square&logo=supabase&labelColor=1c1c1c&color=1c1c1c)](https://axqvoqvbfjpaamphztgd.functions.supabase.co)
[![Leggi la documentazione](https://img.shields.io/badge/Leggi%20la%20documentazione%20Swagger-passing?style=flat-square&logo=Read%20the%20Docs&labelColor=8CA1AF&color=8CA1AF&logoColor=white)](https://samurai016.github.io/Comuni-ITA/)

> ### Legacy project
> Questa repository è la versione aggiornata della repository [Comuni-ITA-legacy](https://github.com/Samurai016/Comuni-ITA-legacy).  
> È possibile usare quella repository per installare una versione standalone dell'API non gestita con Supabase.

Tramite questa REST API hai accesso ad una lista di tutti i comuni, le province e le regioni italiane. I dati sono ottenuti e aggiornamenti da un sistema di aggiornamento semiautomatico che preleva i dati direttamente dagli archivi ISTAT e integra le informazioni mancanti interrogando Wikidata.
I dati non ottenuti automaticamente dal sistema vengono inoltrati direttamente a me che procedo a verificarli e modificarli manualmente.

L'API è scaricabile e installabile su una propria istanza di Supabase oppure è usufruibile in maniera gratuita all'indirizzo https://axqvoqvbfjpaamphztgd.functions.supabase.co.
Dato che l'API è hostata su un servizio gratuito sarebbe opportuno evitare di sovraccaricare l'API per dare a tutti la possibilità di accedervi.

In questa wiki troverai una spiegazione di come funzionano gli endpoint e di come installare l'API su un server.

La documentazione è disponibile anche all'indirizzo https://samurai016.github.io/Comuni-ITA/ sotto forma di documentazione Swagger.

**License:** [MIT](https://opensource.org/licenses/MIT)  
**Credits:** Logo inpired by: [Castle by Jasfart from the Noun Project](https://thenounproject.com/omataloon/)

# Endpoints

## ![GET](https://img.shields.io/static/v1?label=%20&message=GET&color=187bdf&style=flat-square) /comuni

Ottieni la lista di tutti i comuni italiani.

### [Documentazione](https://axqvoqvbfjpaamphztgd.functions.supabase.co/#operation/comuni)

## ![GET](https://img.shields.io/static/v1?label=%20&message=GET&color=187bdf&style=flat-square) /comuni/{regione}

Ottieni la lista di tutti i comuni della regione indicata.

### [Documentazione](https://axqvoqvbfjpaamphztgd.functions.supabase.co/#operation/comuni-regione)

## ![GET](https://img.shields.io/static/v1?label=%20&message=GET&color=187bdf&style=flat-square) /comuni/provincia/{provincia}

Ottieni la lista di tutti i comuni della provincia indicata.

### [Documentazione](https://axqvoqvbfjpaamphztgd.functions.supabase.co/#operation/comuni-provincia)

## ![GET](https://img.shields.io/static/v1?label=%20&message=GET&color=187bdf&style=flat-square) /province

Ottieni la lista di tutte le province italiane.

### [Documentazione](https://axqvoqvbfjpaamphztgd.functions.supabase.co/#operation/province)

## ![GET](https://img.shields.io/static/v1?label=%20&message=GET&color=187bdf&style=flat-square) /province/{regione}

Ottieni la lista di tutte le province della regione indicata.

### [Documentazione](https://axqvoqvbfjpaamphztgd.functions.supabase.co/#operation/province-regione)

## ![GET](https://img.shields.io/static/v1?label=%20&message=GET&color=187bdf&style=flat-square) /regioni

Ottieni la lista delle regioni italiane.

### [Documentazione](https://axqvoqvbfjpaamphztgd.functions.supabase.co/#operation/regioni)

# Dettagli sulle regioni e sulle province

Per evitare incongruenze coi nomi di regioni e province, si consiglia di verificare i nomi attraverso gli endpoint `/regioni` e `/province`.  \
In generale i nomi vanno scritti utilizzando i caratteri speciali come apostrofi, spazi o trattini.

# Installazione su server proprio

Tramite questa repo è possibile installare l'API su una propria istanza di Supabase.

### Sistema di aggiornamento
Il sistema di aggiornamento della API prevede un sistema di logging tramite un bot Telegram. Il bot serve, oltre che per essere notificati sullo stato dell'aggiornamento da remoto, sia per la risoluzione di eventuali problemi/conflitti occorsi durante il fetch automatico dei dati.
Prima di poter installare l'API quindi, crea un bot Telegram tramite [BotFather](https://t.me/botfather) (Puoi chiamarlo come vuoi, il codice per il suo funzionamento è incluso in questa repo). 