# az-800-exams


# Administering Windows Server Hybrid Core Infrastructure AZ-800

Hybrid Identity




> CAPITOLO 1:

<li>
<ol>
  Active Directory
</ol>
</li>


Active Directory è una componente fondamentale in un ambiente Windows Server 
che semplifica la gestione delle risorse di rete, garantendo al contempo sicurezza e coerenza delle informazioni.
Concetti fondamentali di Active Directory:



1. **Directory Service**: Active Directory è un servizio di directory, che funge da database centralizzato per archiviare informazioni sulla rete, come utenti, gruppi, computer, stampanti e risorse condivise. Queste informazioni sono organizzate in un'alberatura gerarchica chiamata "struttura ad albero".

2. **Struttura ad Albero**: Active Directory organizza le risorse di rete in una struttura gerarchica a forma di albero. L'unità di base è il "dominio", che può contenere oggetti come utenti, gruppi e computer. I domini possono essere organizzati in "foreste", che rappresentano un insieme di domini legati tra loro.

3. **Domini e Foreste**: Un dominio è una unità di organizzazione logica e di sicurezza in Active Directory. Una foresta è un insieme di domini che condividono uno schema, una configurazione e un trust reciproco. Gli oggetti all'interno di un dominio o di una foresta possono essere gestiti centralmente.

4. **Utenti e Gruppi**: Active Directory consente di creare e gestire account utente e gruppi. Gli account utente contengono informazioni come nome utente, password e attributi personali, mentre i gruppi possono essere utilizzati per semplificare la gestione delle autorizzazioni e semplificare l'assegnazione di risorse.

5. **Politiche di Gruppo (Group Policies)**: Active Directory consente l'applicazione di Politiche di Gruppo sui computer membri e sugli utenti, consentendo la configurazione centralizzata delle impostazioni di sicurezza, delle restrizioni e delle preferenze di sistema.

6. **Servizi di Sicurezza e Autenticazione**: Active Directory fornisce servizi di autenticazione e autorizzazione, consentendo agli utenti di accedere alle risorse di rete in base ai loro diritti e privilegi. Utilizza protocolli come Kerberos per garantire la sicurezza delle comunicazioni.

7. **Replica dei Dati**: Active Directory utilizza un sistema di replica dei dati per garantire che le informazioni siano coerenti in tutto l'ambiente. I controller di dominio replicano le informazioni tra di loro per garantire la disponibilità e la ridondanza.

8. **DNS Integration**: Active Directory si basa fortemente sulla risoluzione dei nomi DNS (Domain Name System) per identificare e localizzare le risorse nella rete. Un dominio Active Directory è spesso associato a un dominio DNS.

9. **Integrazione con Altri Servizi Microsoft**: Active Directory è ampiamente integrato con altri servizi Microsoft, come Exchange per la gestione delle caselle di posta e SQL Server per la gestione dei database.

10. **Strumenti di Amministrazione**: Gli strumenti di amministrazione come Active Directory Users and Computers (ADUC) e Active Directory Sites and Services (ADSS) forniscono un'interfaccia grafica per la gestione e la configurazione di Active Directory. Inoltre, è possibile utilizzare PowerShell per l'automazione delle attività.


_______________________________________________________________________________

# Concetto di Dominio.


![Screenshot 2024-02-01 alle 11 14 03](https://github.com/MrMagicalSoftware/az-800-exams/assets/98833112/23ce35b0-b164-4267-a361-64e354c77fa1)


In Active Directory, un "dominio" è una unità di organizzazione logica e di sicurezza. Un dominio raggruppa un insieme di risorse, utenti e oggetti di sicurezza in un'unica entità amministrativa all'interno di una rete. le caratteristiche chiave di un dominio in Active Directory:

1. **Unità Amministrativa**: Un dominio rappresenta un'unità di amministrazione, consentendo agli amministratori di gestire utenti, gruppi, computer e risorse all'interno di un singolo contesto organizzativo.

2. **Sicurezza**: I domini forniscono un confine di sicurezza logica all'interno di Active Directory. Gli oggetti di sicurezza, come gli account utente e i gruppi, sono amministrati all'interno del contesto di un dominio, e le policy di sicurezza possono essere applicate a livello di dominio.

3. **Nome del Dominio**: Ogni dominio ha un nome univoco nella rete. Ad esempio, un dominio può essere chiamato "azienda.local". Il nome del dominio è parte integrante dell'indirizzo di rete e può essere utilizzato per accedere alle risorse all'interno del dominio.

4. **Controller di Dominio**: Un dominio è supportato da uno o più controller di dominio. Questi server mantengono una copia del database di Active Directory per il dominio e forniscono servizi di autenticazione, autorizzazione e replica dei dati.

5. **Replica dei Dati**: I controller di dominio all'interno di un dominio si sincronizzano tra loro per garantire la coerenza delle informazioni. La replica dei dati è essenziale per garantire che le modifiche apportate in un controller di dominio vengano propagate agli altri.

6. **Politiche di Gruppo (Group Policies)**: Le Politiche di Gruppo possono essere applicate a livello di dominio. Ciò consente agli amministratori di configurare le impostazioni di sicurezza, le restrizioni e altre configurazioni su tutti i computer e utenti all'interno del dominio.

7. **Namespace DNS Associato**: Ogni dominio Active Directory è associato a uno spazio dei nomi DNS (Domain Name System). Ad esempio, se il nome del dominio è "azienda.local", il corrispondente spazio dei nomi DNS sarà "azienda.local".

8. **Trust**: I domini possono stabilire relazioni di trust con altri domini, consentendo agli utenti di accedere alle risorse in domini diversi. I trust possono essere unidirezionali o bidirezionali.
   
Possiamo pensare che un dominio in Active Directory rappresenta un'entità organizzativa e di sicurezza all'interno di una rete, fornendo un contesto amministrativo e di accesso per gli utenti e le risorse. I domini sono le unità fondamentali su cui è costruita la struttura ad albero di Active Directory.



_______________________________________________________________________________



# Concetto sulla Foresta


Def : una "foresta" è una collezione di domini che condividono uno schema, una configurazione e un trust di sicurezza reciproco. Una foresta rappresenta un limite di sicurezza e amministrativo all'interno di Active Directory ed è la struttura di organizzazione più ampia all'interno del servizio di directory.

Una foresta in Active Directory rappresenta una singola unità organizzativa che collega diversi domini attraverso uno schema, una configurazione e un trust comuni. Ciò consente una gestione centralizzata e controllata delle risorse e delle identità in un ambiente distribuito.




Ecco alcuni concetti chiave relativi alle foreste in Active Directory:

1. **Schema**: Lo schema definisce la struttura e i tipi di oggetti che possono essere archiviati in Active Directory, come utenti, gruppi, computer e risorse. Una foresta condivide uno schema comune tra tutti i domini al suo interno.

2. **Configurazione**: La configurazione di Active Directory contiene informazioni sulle relazioni tra i domini all'interno della foresta, nonché su oggetti e servizi di sistema. Questo include informazioni sui controller di dominio, le repliche e altri aspetti della configurazione globale.

3. **Trust**: Una foresta costituisce una barriera di sicurezza e amministrativa, ma è possibile stabilire relazioni di trust tra le foreste per consentire la condivisione controllata delle risorse. I trust possono essere unidirezionali o bidirezionali.

4. **Struttura ad Albero**: All'interno di una foresta, i domini sono organizzati in una struttura ad albero. Ogni dominio rappresenta un'unità di amministrazione e sicurezza, ma la foresta rappresenta il livello più alto di organizzazione che li collega.

5. **Gestione Centralizzata**: Una foresta consente la gestione centralizzata degli oggetti, delle policy e delle risorse tra i domini. Ciò semplifica la gestione delle identità e delle risorse in un ambiente distribuito.

6. **Namespace DNS Comune**: Tutti i domini all'interno di una foresta condividono uno spazio dei nomi DNS comune, il che significa che i nomi dei domini sono correlati tra loro. Ad esempio, se un dominio è denominato "dominio1.contoso.com", un altro dominio nella stessa foresta potrebbe essere "dominio2.contoso.com".

7. **Ridondanza e Affidabilità**: Una foresta offre ridondanza e affidabilità attraverso la presenza di più controller di dominio in domini diversi. La replica dei dati e dei servizi tra i controller di dominio contribuisce a garantire la disponibilità delle informazioni.




![Screenshot 2024-02-01 alle 11 11 40](https://github.com/MrMagicalSoftware/az-800-exams/assets/98833112/367bdce5-5e4a-41a9-a19a-a723b02b6284)


______________________________________________________


# Concetto di tree ( albero )

![Screenshot 2024-02-01 alle 11 22 40](https://github.com/MrMagicalSoftware/az-800-exams/assets/98833112/b260551f-8f6e-44ec-bb9b-c59a9d725820)



In Active Directory, un "albero" si riferisce alla struttura gerarchica di domini collegati tra loro. La combinazione di più domini organizzati in modo gerarchico costituisce la struttura ad albero di Active Directory. Ecco alcune informazioni chiave riguardo a questa struttura:

Un albero in Active Directory rappresenta una struttura gerarchica di domini collegati tra loro, consentendo una gestione organizzata e centralizzata delle risorse e delle identità all'interno di una rete. La struttura ad albero offre una flessibilità organizzativa e amministrativa all'interno di Active Directory.


1. **Struttura Gerarchica**: Un albero di Active Directory è una struttura organizzata gerarchicamente in cui i domini sono collegati in una relazione padre-figlio. Il dominio al livello più alto dell'albero è noto come "dominio radice", e i domini successivi costituiscono i "domini figlio".

2. **Relazione Padre-Figlio**: Ogni dominio, ad eccezione del dominio radice, è legato al dominio genitore attraverso una relazione padre-figlio. Ad esempio, se si ha un dominio radice chiamato "azienda.local", è possibile avere domini figlio come "vendite.azienda.local" e "produzione.azienda.local".

3. **Nome Completo del Dominio**: Il nome completo del dominio (Fully Qualified Domain Name o FQDN) di un dominio figlio include il nome del dominio figlio e il nome completo del dominio genitore. Ad esempio, il FQDN per il dominio figlio "vendite" potrebbe essere "vendite.azienda.local".

4. **Trust tra Domini**: I domini all'interno dell'albero possono stabilire relazioni di trust tra di loro. Ciò consente agli utenti di un dominio di accedere alle risorse in altri domini dell'albero senza dover reinserire le credenziali.

5. **Politiche di Gruppo (Group Policies)**: Le Politiche di Gruppo possono essere applicate a livello di albero, consentendo agli amministratori di configurare le impostazioni di sicurezza e di configurazione su tutti i domini all'interno della struttura ad albero.

6. **Namespace DNS Associato**: Ogni dominio all'interno dell'albero è associato a uno spazio dei nomi DNS. Il nome del dominio, insieme al nome del dominio genitore, costituisce il FQDN utilizzato per identificare univocamente un dominio all'interno dell'albero.

7. **Gestione Centralizzata**: Nonostante ogni dominio abbia la sua amministrazione locale, la struttura ad albero di Active Directory consente una gestione centralizzata attraverso l'applicazione coerente di politiche di sicurezza e configurazioni su tutti i domini.

___________________________________________________


# Concetto di schema 


Lo "schema" in Active Directory è una parte fondamentale del servizio di directory e definisce la struttura e i tipi di oggetti che possono essere archiviati nel database di Active Directory. Questo include oggetti come utenti, gruppi, computer, stampanti e altri oggetti di sistema. Ecco alcuni punti chiave relativi allo schema in Active Directory:

 lo schema in Active Directory funge da "schema dati" per la struttura e i tipi di oggetti che possono essere archiviati. È una componente critica per la coerenza e la gestione delle informazioni all'interno del servizio di directory.


1. **Definizione degli Oggetti**: Lo schema specifica quali attributi e quali tipi di oggetti possono essere memorizzati in Active Directory. Ad esempio, definisce cosa costituisce un oggetto utente, quali attributi contiene (come nome utente, password, ecc.) e come sono strutturati.

2. **Struttura Gerarchica**: Gli oggetti all'interno dello schema sono organizzati in una struttura gerarchica. Ciò riflette la relazione tra diversi tipi di oggetti e attributi. La struttura gerarchica è essenziale per mantenere l'ordine e la coerenza delle informazioni.

3. **Estensione dello Schema**: In alcuni casi, è possibile estendere lo schema per includere nuovi attributi o oggetti personalizzati che soddisfano requisiti specifici dell'organizzazione. Questa estensione dello schema deve essere gestita attentamente per evitare problemi di compatibilità.

4. **Configurazione Globale**: Le informazioni relative allo schema sono memorizzate nella partizione di configurazione di Active Directory, che è globale per l'intera foresta. Ciò significa che lo schema è condiviso tra tutti i domini all'interno della foresta.

5. **Versioning**: Lo schema è soggetto a versioning, il che significa che può essere aggiornato nel corso del tempo. Gli amministratori possono apportare modifiche allo schema per adattarsi alle esigenze dell'organizzazione o per integrare nuove funzionalità.

6. **DNS e Nomi Univoci**: Lo schema contribuisce a definire la struttura dei nomi all'interno di Active Directory. Ad esempio, il nome di un attributo può essere univoco in tutto lo schema, garantendo così la coerenza nelle definizioni degli oggetti.

7. **Limitazioni e Autorizzazioni**: La modifica dello schema richiede privilegi elevati e deve essere effettuata con attenzione. Gli amministratori devono avere i diritti appropriati per apportare modifiche allo schema.

8. **Compatibilità**: La coerenza nello schema è fondamentale per garantire la compatibilità tra i vari servizi e applicazioni che fanno uso di Active Directory. Le modifiche allo schema devono essere gestite con attenzione per evitare problemi di interoperabilità.



_______________________


# Concetti Fondamentali per iniziare :
> Domain
> Tree
> Forest
> Schema



Review dei concetti .


Certamente! Ecco alcune domande a risposta multipla riguardo a Domain, Tree, Forest e Schema:

### Domain:

1. **Cosa rappresenta un dominio in Active Directory?**
   - A) Una unità di organizzazione fisica
   - B) Una unità di organizzazione logica e di sicurezza
   - C) Un singolo computer in una rete
   - D) Un tipo di albero nella struttura di Active Directory

2. **Qual è la funzione principale di un dominio in Active Directory?**
   - A) Fornire accesso a Internet
   - B) Organizzare gli oggetti di sicurezza e di rete
   - C) Gestire le stampanti di rete
   - D) Aggiornare automaticamente i software sui computer client

### Tree:

3. **Cosa rappresenta un albero in Active Directory?**
   - A) Una collezione di oggetti utente
   - B) Una struttura gerarchica di domini collegati
   - C) Una configurazione di rete wireless
   - D) Una serie di gruppi di lavoro connessi

4. **Qual è la relazione principale tra i domini in un albero di Active Directory?**
   - A) Parente-figlio
   - B) Fratello-sorella
   - C) Non ci sono relazioni tra i domini
   - D) Bidirezionale

### Forest:

5. **Cosa è una foresta in Active Directory?**
   - A) Una collezione di alberi
   - B) Un singolo dominio di rete
   - C) Una struttura ad albero con radice
   - D) Un gruppo di server Web

6. **Cosa condivide una foresta in Active Directory tra tutti i domini al suo interno?**
   - A) Schema, configurazione e trust di sicurezza
   - B) Solo gli oggetti utente
   - C) Solo le Politiche di Gruppo
   - D) Solo i nomi dei computer

### Schema:

7. **Cosa rappresenta lo schema in Active Directory?**
   - A) Una collezione di immagini di sfondo
   - B) La struttura di un sito web
   - C) La definizione degli oggetti e degli attributi in Active Directory
   - D) Una serie di protocolli di rete

8. **Dove sono memorizzate le informazioni relative allo schema in Active Directory?**
   - A) Nella partizione di dominio
   - B) Nella partizione di applicazione
   - C) Nella partizione di configurazione
   - D) In un file di testo sul server principale


Risposte alle domande :

1-B
2-B
3-B
4-A
5-A
6-A
7-C
8-C


___________________________________________________________


# COMPONENTI LOGICHE E COMPONENTI FISICHE :


The following can be considered as the logical components:


<li> Domain</li>
<li> Domain tree</li>
<li> Forest</li>
<li> OU</li>
<li> Partition</li>
<li> Schema</li>
<li> Container</li>


<br>
The following can be considered as the physical components:<br>
<br>




<li> Data store</li>
<li> Global catalog</li>
<li> Domain controller</li>
<li> Read-only domain controller</li>
<li> Site</li>
<li> Subnet</li>




# CONTAINER OBJECTS


![Screenshot 2024-02-01 alle 11 40 40](https://github.com/MrMagicalSoftware/az-800-exams/assets/98833112/494360ca-992b-402f-85dc-b1ac805ee52a)

In Active Directory, un "container" è un tipo di oggetto che viene utilizzato per organizzare e contenere altri oggetti. I container forniscono una struttura gerarchica all'interno di un dominio e sono utilizzati per raggruppare e organizzare gli oggetti in un contesto specifico. 

 i containers in Active Directory fungono da contenitori logici per organizzare e raggruppare gli oggetti. Sono una parte essenziale della struttura gerarchica del servizio di directory, contribuendo alla gestione organizzativa e alla sicurezza nell'ambiente di rete.


1. **Definizione di Container**:
   - Un container è un tipo di oggetto di Active Directory utilizzato per organizzare altri oggetti, come utenti, gruppi e computer. I container possono essere pensati come contenitori logici in cui gli oggetti sono raggruppati in base a una determinata logica organizzativa.

2. **Differenza tra Container e Organizational Unit (OU)**:
   - Sia i containers che le Organizational Units (OU) sono utilizzati per organizzare oggetti, ma ci sono alcune differenze importanti. Gli oggetti all'interno di un container ereditano le impostazioni del dominio, mentre un'OU consente la delega di autorità e l'applicazione di Politiche di Gruppo specifiche.

3. **Esempi di Containers Predefiniti**:
   - Alcuni containers predefiniti in Active Directory includono:
      - **Users**: Contiene account utente.
      - **Computers**: Contiene account computer.
      - **Domain Controllers**: Contiene i controller di dominio del dominio.
      - **System**: Contiene oggetti di sistema.

4. **Accesso ai Containers**:
   - L'accesso ai containers è determinato dalle autorizzazioni. Gli amministratori possono avere diritti di accesso diversi a diversi containers. Ad esempio, un amministratore potrebbe avere accesso completo a un container "Users" ma solo accesso di lettura a un container "System".

5. **Creazione di Nuovi Containers**:
   - A differenza di alcune altre strutture in Active Directory, i containers non possono essere creati direttamente dall'utente. Sono spesso creati automaticamente quando vengono creati oggetti all'interno di Active Directory.

6. **Ruolo nei Livelli di Sicurezza e Organizzazione**:
   - I containers svolgono un ruolo importante nella gestione della sicurezza e nella struttura organizzativa di Active Directory. Consentono agli amministratori di applicare autorizzazioni specifiche e organizzare gli oggetti in modo coerente.

7. **Replica dei Dati**:
   - Le informazioni all'interno dei containers vengono replicate tra i controller di dominio per garantire la coerenza delle informazioni in tutto l'ambiente Active Directory.



NOTA :

La principale differenza tra un “container” e un’ “Organizational Unit (OU)” in Active Directory è la capacità di applicare politiche di gruppo e di delegare le autorizzazioni. 
Le OU sono progettate per essere utilizzate come contenitori all’interno dei quali gli amministratori di sistema possono applicare politiche di gruppo (GPO) e possono delegare controlli o autorizzazioni amministrative su subset di oggetti all’interno dell’Active Directory. Inoltre, le OU possono essere annidate, permettendo una struttura gerarchica che facilita la gestione e l’organizzazione.

D’altra parte, i container, come “Users” o “Computers”, sono oggetti predefiniti in Active Directory che non hanno la stessa flessibilità delle OU.
Non si possono applicare direttamente le GPO ai container e non è possibile delegare le autorizzazioni in modo granulare come si farebbe con le OU. Inoltre, i container non possono essere annidati come le OU, quindi la loro capacità organizzativa è più limitata.
se si ha bisogno di una struttura flessibile per applicare politiche di gruppo e per delegare autorizzazioni a diversi amministratori o gruppi di amministratori, bisogna utilizzare le OU piuttosto che i container predefiniti.



# DOMANDE DI RIPASSO :


1. **Cosa rappresenta un "container" in Active Directory?**
   - A) Un tipo di server
   - B) Un oggetto di sicurezza
   - C) Un oggetto utilizzato per organizzare altri oggetti
   - D) Un livello di accesso alle risorse

2. **Quale dei seguenti è un esempio di container predefinito in Active Directory?**
   - A) Organizational Unit (OU)
   - B) Schema
   - C) Forest
   - D) Users

3. **Qual è la principale differenza tra un "container" e un' "Organizational Unit (OU)" in Active Directory?**
   - A) Gli oggetti in un container non possono ereditare le impostazioni
   - B) Le OU sono utilizzate solo per organizzare utenti
   - C) I container non possono contenere altri oggetti
   - D) Gli oggetti in una OU ereditano le impostazioni del dominio

4. **Qual è il ruolo principale di un container in Active Directory?**
   - A) Fornire accesso a Internet
   - B) Organizzare oggetti in un contesto specifico
   - C) Applicare Politiche di Gruppo
   - D) Creare nuovi domini

5. **Come vengono gestiti gli accessi ai containers in Active Directory?**
   - A) Attraverso una chiave fisica
   - B) Attraverso autorizzazioni specifiche
   - C) Utilizzando un nome utente generico
   - D) Automaticamente senza necessità di gestione

6. **Dove sono memorizzate le informazioni relative ai containers in Active Directory?**
   - A) Nella partizione di dominio
   - B) Nella partizione di schema
   - C) Nella partizione di configurazione
   - D) In un file di testo sul server principale

Risposte:
1. C) Un oggetto utilizzato per organizzare altri oggetti
2. D) Users
3. A) Gli oggetti in un container non possono ereditare le impostazioni
4. B) Organizzare oggetti in un contesto specifico
5. B) Attraverso autorizzazioni specifiche
6. C) Nella partizione di configurazione

________

































