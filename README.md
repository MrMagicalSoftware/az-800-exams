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


