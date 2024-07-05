> Avvertenza: Questa pagina è dedicata ad un'idea per un progetto ancora in fase di sviluppo, pertanto sia l'idea che il risultato finale possono essere modificati o scartati in qualsiasi momento.

Internet Avatar è stato pensato come un sistema per riunire molteplici account.
Ogni account richiede per la creazione solo un nome utente, una password e un [identificatore (IDF)](#Gli%20Identificatori%20(IDF)). Dentro l'account sono salvati un *ID unico*, [applicazioni](#Applicazioni), [il numero di crediti](#I%20Crediti), gli atti di moderazione, [i permessi](#i%20permessi) e [una pagina dedicata](#Le%20Pagine).
# Gli Identificatori (IDF)
Gli identificatori sono semplici dati di accesso, come per esempio una mail, un numero di telefono, un ID discord...
Normalmente la trasmissione avviene sotto questa forma: `TYPE:VALUE`, dove abbiamo come value il vero e proprio IDF, mentre come type uno di quelli sottostanti:

| Type      | Descrizione                  | Verifica                                                                     |
| --------- | ---------------------------- | ---------------------------------------------------------------------------- |
| `EMAIL`   | Semplice E-Mail              | Codice/Link inviato via mail                                                 |
| `DISCORD` | Salvato solo l'ID di Discord | OAuth2 / `/verify` (app autorizzata) / Reazione a notifica (app autorizzata) |

# I Crediti
Salvati come numero dentro ogni account, l'idea dei crediti è creare una valuta virtuale facile e veloce da utilizzare.
Il valore è stato pensato come circa `1000 crediti = 1 euro` in maniera da facilitarne la vendita.
## L'acquisizione
E' possibile acquisire crediti nelle seguenti maniere:
- Pagare il rispettivo prezzo a Thunder Network o a un Authorized Credit Creator.
- Svolgere missioni da TN o da uno dei partner.
## L'utilizzo
E' possibile utilizzare i crediti nelle seguenti maniere:
- Pagare un altro utente
- Pagare un oggetto in uno store digitale che supporta i crediti
- Acquisti in-app
## API
L'**accesso in lettura** ai crediti sarà pubblico.
L'**accesso in modifica** ai crediti sarà accessibile a qualsiasi sviluppatore verificato, che potrà utilizzarlo senza pagare in qualsiasi app o prodotto. *Possono essere applicate tariffe percentuali sulle transazioni di app terze*.
# Applicazioni
Gli sviluppatori verificati potranno registrare applicazioni, ogni applicazione avrà l'accesso a:
- [I Permessi](#I%20Permessi)
- [I Crediti](#I%20Crediti) con "banca" dedicata all'applicazione
- [una pagina dedicata](#Le%20Pagine)
## I Permessi
Per semplificare la vita ai creatori di comunità e gruppi, abbiamo scelto di inserire dentro Internet Avatar un sistema di permessi.
Ogni sviluppatore verificato potrà decidere di aggiungere dei permessi in stile `minecraft.ban`, questo sistema è stato creato in maniera che `minecraft.ban` includa tutti i sotto-permessi come `minecraft.ban.perm`, `minecraft.ban.temp`, `minecraft.ban.remove` ...
# Gruppi / Comunità
Ogni account IA potrà registrare una o più comunità, ogni comunità potrà:
- registrare i [permessi](#I%20Permessi) ai suoi utenti
- avere un conto per i [crediti](#I%20Crediti) dedicato alla comunità.
- registrare [Applicazioni](#Applicazioni) alla sua comunità
- [una pagina dedicata](#Le%20Pagine)
# Le Pagine
Il layout della pagina sarà un template, ogni pagina potrà essere personalizzata con una descrizione e un titolo. Potranno essere create sotto-pagine e nella pagina principale può essere abilitato un blog.
## Il blog
Il blog potrà essere utilizzato normalmente per inviare testi o contenuti multimediali. Inoltre si potrà abilitare l'importazione automatica da i social che lo supportano, mostrando così post su youtube, x, ecc.
Ogni post, importato e non, potrà essere messo pubblico, non in elenco o privato (per aggiungere una persona si potrà registrare un permesso specifico).