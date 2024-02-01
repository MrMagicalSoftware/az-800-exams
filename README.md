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


In Active Directory, un "dominio" è una unità di organizzazione logica e di sicurezza. Un dominio raggruppa un insieme di risorse, utenti e oggetti di sicurezza in un'unica entità amministrativa all'interno di una rete. Ecco alcune caratteristiche chiave di un dominio in Active Directory:

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











