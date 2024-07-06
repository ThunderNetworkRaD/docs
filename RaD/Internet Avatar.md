> Avvertenza: Questa pagina è dedicata ad un'idea per un progetto ancora in fase di sviluppo, pertanto sia l'idea che il risultato finale possono essere modificati o scartati in qualsiasi momento.

Internet Avatar è stato pensato come un sistema per riunire molteplici account.
Ogni account richiede per la creazione solo un nome utente, una password e un [identificatore (IDF)](#Gli%20Identificatori%20(IDF)). Dentro l'account sono salvati un *ID unico*, [applicazioni](#Applicazioni), [il numero di crediti](#I%20Crediti), [la Fedina Penale](#La%20Fedina%20Penale), [i permessi](#i%20permessi), [una pagina dedicata](#Le%20Pagine) e i [token](#I%20token).
# Gli Identificatori (IDF)
Gli identificatori sono semplici dati di accesso, come per esempio una mail, un numero di telefono, un ID discord...
Normalmente la trasmissione avviene sotto questa forma: `TYPE:VALUE`, dove abbiamo come value il vero e proprio IDF, mentre come type uno di quelli sottostanti:

| Type      | Descrizione                  | Verifica                                                                     |
| --------- | ---------------------------- | ---------------------------------------------------------------------------- |
| `EMAIL`   | Semplice E-Mail              | Codice/Link inviato via mail                                                 |
| `DISCORD` | Salvato solo l'ID di Discord | OAuth2 / `/verify` (app autorizzata) / Reazione a notifica (app autorizzata) |

# I Crediti
Salvati come numero dentro ogni account, l'idea dei crediti è creare una valuta virtuale facile e veloce da utilizzare.
Il valore è stato pensato come circa `1000 crediti = 1 euro` facilitandone la vendita.
## L'acquisizione
E' possibile acquisire crediti nei seguenti modi:
- Pagare il rispettivo prezzo a Thunder Network o a un Authorized Credit Creator.
- Svolgere missioni da TN o da uno dei partner.
## L'utilizzo
E' possibile utilizzare i crediti nelle seguenti modi:
- Pagare un altro utente
- Pagare un oggetto in uno store digitale che supporta i crediti
- Acquisti in-app
## API
L'**accesso in lettura** ai crediti sarà pubblico.
L'**accesso in modifica** ai crediti sarà accessibile a qualsiasi sviluppatore verificato, che potrà utilizzarlo senza pagare in qualsiasi app o prodotto. *Possono essere applicate tariffe percentuali sulle transazioni di app terze*.
# La Fedina Penale
La fedina penale è la lista di tutti gli atti di moderazione eseguiti sull'utente.
Gli atti saranno divisi in **verificati** e **non verificati**.
Quelli **verificati** saranno visibili in cima alla lista di tutti gli atti. Sono quegli atti con prove sufficienti (inviate) da poter essere verificati da una commissione esterna.
Quelli **non verificati** saranno visibili sotto a quelli verificati.

I moderatori di un gruppo possono abilitare gli avvisi all'ingresso, in cui si riceve una notifica se un utente con *"la fedina penale sporca"* entra nella comunità. Si può scegliere se abilitarla solo per gli atti verificati o anche per quelli non verificati.

I gestori della community possono decidere di abilitare [le liste di proscrizione](#Le%20liste%20di%20proscrizione), per cui, se un utente è stato aggiunto, non può entrare nella comunità.
## La verifica
La verifica degli atti di moderazione verrà eseguita dai moderatori di TN e dei partner, dopo la verifica si riceverà una notifica che avvisa l'utente segnalatore e l'utente segnalato.

L'utente segnalatore potrà inviare la richiesta per aggiungere l'utente segnalato alle liste di proscrizione tramite la notifica della verifica. In questo caso l'atto verrà ri-verificato da 3 moderatori **diversi** da quello iniziale, randomici e anonimi.
# Applicazioni
Gli sviluppatori verificati potranno registrare applicazioni, ogni applicazione avrà l'accesso a:
- [I Permessi](#I%20Permessi)
- [I Crediti](#I%20Crediti) con "banca" dedicata all'applicazione
- [una pagina dedicata](#Le%20Pagine)
# I Permessi
Per semplificare la vita ai creatori di comunità e gruppi, abbiamo scelto di inserire dentro Internet Avatar un sistema di permessi.
Ogni sviluppatore verificato potrà decidere di aggiungere dei permessi in stile `minecraft.ban`, questo sistema è stato creato  facendo che `minecraft.ban` includa tutti i sotto-permessi, come `minecraft.ban.perm`, `minecraft.ban.temp`, `minecraft.ban.remove` ...
## Permessi
### Per account

| Permesso           | Descrizione                                      |
| ------------------ | ------------------------------------------------ |
| `user.<id>`        | Permette di modificare l'utente con id `<id>`    |
| `.api.createToken` | Permette di creare un token per accedere all'API |

### Speciali

| Permesso  | Descrizione                       |
| --------- | --------------------------------- |
| `user`    | Permette di modificare gli utenti |
| `.create` | Permette di creare un utente      |
| `.delete` | Permette di eliminare un utente   |

# I token
Esistono due tipi di token, [i token API](#I%20token%20API) e [i token di sessione](#I%20token%20di%20sessione).
## I token API
I token API sono codici univoci di 64 caratteri con permessi personalizzati che possono essere generati manualmente, il loro scopo è l'accesso agli endpoint dell'API.
## I token di sessione
I token di sessione sono codici univoci di 128 caratteri generati automaticamente durante un log-in. Hanno tutti i permessi che l'utente possiede ma hanno una durata limitata, personalizzabile durante il log-in.
Tra i loro principali scopi c'è la creazione de[i token API](#I%20token%20API)
# Gruppi / Comunità
Ogni account IA potrà registrare una o più comunità, ogni comunità potrà:
- registrare i [permessi](#I%20Permessi) ai suoi utenti
- avere un conto per i [crediti](#I%20Crediti) dedicato alla comunità.
- registrare [Applicazioni](#Applicazioni) alla sua comunità
- [una pagina dedicata](#Le%20Pagine)
- le [liste di proscrizione](#Le%20liste%20di%20proscrizione)
# Le Pagine
Il layout della pagina sarà un template, ogni pagina potrà essere personalizzata con una descrizione e un titolo. Potranno essere create sotto-pagine e nella pagina principale può essere abilitato un blog.
## Il blog
Il blog potrà essere utilizzato normalmente per inviare testi o contenuti multimediali. Inoltre si potrà abilitare l'importazione automatica da i social che lo supportano, mostrando così post su youtube, x, ecc.
Ogni post, importato e non, potrà essere messo pubblico, non in elenco o privato (per aggiungere una persona si potrà registrare un permesso specifico).
## Le liste di proscrizione
Sono liste di utenti che hanno commesso atti gravi contro la comunità.
Le liste sono facoltative, e se abilitate si possono usare sia espellendo l'utente dalla comunità che mettendolo in quarantena.
Ogni server può sovrascrivere le liste annullando l'atto di una persona, permettendogli così la permanenza.

La verifica della causa per cui l'utente è stato aggiunto alla lista di proscrizione sarà effettuata da 3 moderatori di TN o partner, diversi dal moderatore della prima [verifica](#La%20verifica).

E' garantita la possibilità di fare 3 appelli per lo stesso provvedimento.