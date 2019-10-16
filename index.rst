­­Linee Guida contenenti le

Regole Tecniche circa la sottoscrizione elettronica di documenti
mediante SPID ex art. 20 del CAD tramite il sistema SPID

Sommario
========

`1 Definizioni 3 <#definizioni>`__

`2 Scopo e ambito di applicazione 4 <#scopo-e-ambito-di-applicazione>`__

`3 Procedura di sottoscrizione ex articolo 20 comma 1bis del CAD
4 <#procedura-di-sottoscrizione-ex-articolo-20-comma-1bis-del-cad>`__

`3.1 Predisposizione alla sottoscrizione (presso il SP)
4 <#predisposizione-alla-sottoscrizione-presso-il-sp>`__

`3.2 Consenso alla sottoscrizione (presso l’\ IdP)
5 <#consenso-alla-sottoscrizione-presso-lidp>`__

`4 Regole tecniche del documento sottoscritto
6 <#regole-tecniche-del-documento-sottoscritto>`__

`4.1 Formato del documento 6 <#formato-del-documento>`__

`4.2 Convenzioni di nomenclatura dei documenti
6 <#convenzioni-di-nomenclatura-dei-documenti>`__

`4.3 Apposizione del q\ Seal del Service Provider
7 <#apposizione-del-qseal-del-service-provider>`__

`4.4 Apposizione del q\ Seal dell’Identity Provider
7 <#apposizione-del-qseal-dellidentity-provider>`__

`4.5 Certificati di sigillo elettronico qualificato
7 <#certificati-di-sigillo-elettronico-qualificato>`__

`5 Richieste e risposte di autenticazione per la firma
9 <#richieste-e-risposte-di-autenticazione-per-la-firma>`__

`5.1 SAML 9 <#saml>`__

`5.2 Sistema di trasferimento sicuro dei documenti 10 <#_Ref14164792>`__

`5.2.1 Interfaccia applicativa 11 <#interfaccia-applicativa>`__

`6 Algoritmi crittografici 15 <#algoritmi-crittografici>`__

`7 Codici di errore 15 <#codici-di-errore>`__

`8 Obblighi degli enti federati 16 <#obblighi-degli-enti-federati>`__

`8.1 Obblighi in capo agli Identity Provider
16 <#obblighi-in-capo-agli-identity-provider>`__

`8.2 Obblighi in capo ai Service Provider
16 <#obblighi-in-capo-ai-service-provider>`__

`9 Servizio di conservazione dei documenti firmati
16 <#servizio-di-conservazione-dei-documenti-firmati>`__

`10 Norme transitorie 16 <#norme-transitorie>`__

Definizioni
===========

Ai fini delle presenti Linee guida, oltre ad applicarsi le definizioni
di cui all’articolo 1 del CAD, si intende per:

-  Agenzia o AgID: Agenzia per l’Italia Digitale;

-  CAD: D.Lgs. 7 marzo 2005 N°82, *Codice dell’Amministrazione
   Digitale*, e sue successive modificazioni;

-  documento firmato con SPID: il documento cui è apposto il sigillo
   elettronico qualificato dell’\ IdP;

-  ente federato: gestore di identità digitali ovvero fornitore di
   servizi della federazione SPID;

-  firma: vedi sottoscrizione;

-  firmatario: la persona fisica che, utilizzando la propria identità
   digitale SPID di livello 2 o superiore, conferisce al documento
   informatico il valore e l’efficacia previsti dall’articolo 20 del CAD
   attraverso il processo di firma di cui al presente provvedimento;

-  impronta: impronta crittografica, risultante dell’applicazione di una
   funzione di *hash* crittografico ad un’evidenza informatica;

-  ll.gg. sui certificati elettronici: *Linee guida contenenti Regole
   Tecniche e Raccomandazioni afferenti la generazione di certificati
   elettronici qualificati, firme e sigilli elettronici qualificati e
   validazioni temporali elettroniche qualificate*, pubblicate con
   Determinazione AgID N°121/2019 e successive modificazioni;

-  ll.gg. sulle misure minime di sicurezza: Circolare AgID N°1/2017 e
   successive modificazioni, recante *Misure minime di sicurezza ict per
   le pubbliche amministrazioni*, emanata con dpcm del 24 ottobre 2014;

-  OpenAPI\ *®*: *OpenAPI Specification* (oas), versione 3.0;

-  registro SPID: elenco dei soggetti appartenenti alla federazione
   SPID, previsto dalla vigente normativa;

-  regolamento eIDAS: Regolamento (ue) N°910/2014 del Parlamento Europeo
   e del Consiglio, del 23 luglio 2014, in materia di identificazione
   elettronica e servizi fiduciari per le transazioni elettroniche nel
   mercato interno e che abroga la direttiva 1999/93/\ ce;

-  regolamento GDPR: Regolamento (ue) N°679/2016 del Parlamento Europeo
   e del Consiglio, del 27 aprile 2016, relativo alla protezione delle
   persone fisiche con riguardo al trattamento dei dati personali,
   nonché alla libera circolazione di tali dati e che abroga la
   direttiva 95/46/\ ce;

-  richiesta di autenticazione: l’evidenza informatica con la quale un
   SP richiede l’avvio di una sessione di autenticazione presso un IdP
   (cioè l’\ *authentication request*);

-  risposta di autenticazione: l’evidenza informatica con la quale un
   IdP comunica i dati personali, o il diniego a fornirli, presso un SP
   (*response*);

-  sottoscrizione: il processo di cui all’articolo 20, comma 1-bis, del
   CAD.

-  titolare della piattaforma: il soggetto pubblico o privato che, in
   qualità di SP, rende possibile a un firmatario la formazione di un
   documento informatico per via telematica, al fine di conferirgli il
   valore e l’efficacia previsti dall’articolo 20 del CAD.

Sono anche utilizzati i seguenti acronimi o abbreviazioni:

-  api: interfaccia applicativa (*application programming interface*);

-  IdP: gestore di identità digitali nel contesto della federazione
   SPID;

-  json: *JavaScript Object Notation*, come previsto dalle norme
   `RFC-8259 <https://tools.ietf.org/html/rfc8259>`__;

-  jwa: algoritmi crittografici json (*JSON Web Algorithm*), come
   previsto dalle norme
   `RFC-7518 <https://tools.ietf.org/html/rfc7518>`__;

-  jws: pacchetto jwt firmato (*JSON Web Token Signature*), come
   previsto dalle norme
   `RFC-7515 <https://tools.ietf.org/html/rfc7515>`__;

-  jwt: pacchetto json per applicazioni web (*JSON Web Token*), come
   previsto dalle norme
   `RFC-7797 <https://tools.ietf.org/html/rfc7797>`__.

-  q\ Seal: sigillo elettronico qualificato, come da regolamento
   e\ IDAS;

-  qtsp: prestatore di servizi fiduciari elettronici qualificati, come
   da regolamento e\ IDAS;

-  saml: standard `Security Assertion Markup
   Language <http://docs.oasis-open.org/security/saml/v2.0/saml-2.0-os.zip>`__,
   versione 2.0, pubblicato da
   `oasis <https://www.oasis-open.org/standards>`__;

-  SP: fornitore di servizi nella federazione SPID, ovvero *service
   provider* nel contesto saml, ovvero *relying party* nel contesto
   oidc;

-  SPID: il Sistema Pubblico di Identità Digitale.

Scopo e ambito di applicazione
==============================

L’articolo 20 del CAD dispone il soddisfacimento del requisito della
forma scritta e l’efficacia prevista dall’articolo 2702 del Codice
Civile del documento informatico formato previa identificazione
informatica del suo autore, *attraverso un processo avente i requisiti
fissati dall’AgID ai sensi dell’articolo 71 con modalità tali da
garantire la sicurezza, integrità e immodificabilità del documento e, in
maniera manifesta e inequivoca, la sua riconducibilità all’autore*.

Le presenti Linee guida regolano le modalità atte a garantire la
sicurezza, integrità e immodificabilità del documento e, in maniera
manifesta e inequivoca, la sua riconducibilità all’autore.

Procedura di sottoscrizione ex articolo 20 comma 1bis del CAD
=============================================================

Il processo di cui all’articolo 20 comma 1\ *bis* del CAD non può essere
adoperato utilizzando identità digitali SPID per persona giuridica;
possono essere utilizzate esclusivamente le identità digitali della
persona fisica e le identità digitali per uso professionale.

Tutti i SP interessati hanno il diritto di avvalersi del servizio in
oggetto.

I metadati SPID indicano se l’\ IdP offre il servizio in oggetto.

Il servizio di sottoscrizione oggetto delle presenti Linee guida è
realizzato per permettere al medesimo utente di sottoscrivere una o più
parti del medesimo documento, attraverso un’unica sessione di
autenticazione SPID e, al contempo, a utenti distinti di sottoscrivere
il medesimo documento, in tempi e con sessioni di autenticazione SPID
distinte.

Il processo di firma prevede che l’utente, tramite il SP, esegua un
processo di autenticazione al fine della firma, con la propria identità
digitale di livello 2 o superiore, scegliendo il proprio IdP. Per la
scelta dell’\ IdP, il SP mostra solo gli IdP che offrono tale servizio.

Predisposizione alla sottoscrizione (presso il SP)
--------------------------------------------------

Il processo prevede quanto segue:

1. Il SP predispone il documento, apponendovi un proprio sigillo
   elettronico qualificato, secondo quanto prescritto tecnicamente nel
   §4.1, sottoponendolo, presso la propria piattaforma, all’utente
   affinché possa essere visionato, eventualmente scaricato e
   conservato.

2. Il SP richiede all’utente conferma della volontà di procedere alla
   sottoscrizione del documento di cui al punto 1, rendendo manifesto
   che il processo prevede l’invio del documento all’\ IdP prescelto,
   acquisendo quindi il consenso dell’utente. L’utente è avvisato in
   modo chiaro e manifesto che tale documento gli sarà reso
   successivamente disponibile dal proprio IdP e gli viene consigliato
   di leggerlo nuovamente in tale occasione.

3. Il SP inoltra la sessione dell’utente all’\ IdP con una nuova
   richiesta di autenticazione speciale (di livello pari almeno a 2),
   denominata “firma SPID“, conforme alle caratteristiche tecniche di
   cui al §5 e invia il documento predisposto al punto 1 all’\ IdP con
   le modalità descritte nel §5.2.

Consenso alla sottoscrizione (presso l’\ IdP)
---------------------------------------------

   L’\ IdP:

4.  Procede con l’autenticazione dell’utente con credenziali di livello
    2 o superiore.

5.  Informa l’utente che il processo di autenticazione è volto alla
    sottoscrizione, comunicando all’utente:

    -  il nome del SP che sta richiedendo la sottoscrizione del
       documento,

    -  il nome del file contenente il documento in oggetto.

6.  Consente all’utente di visionare il documento e scaricarlo.

7.  Propone all’utente di procedere con la sottoscrizione. Il dissenso
    alla sottoscrizione da parte dell’utente comporta l’invio di una
    risposta di autenticazione con esito negativo al SP e il termine del
    processo.

8.  Visualizza la pagina destinata a contenere il contenuto grafico del
    sigillo elettronico qualificato informando l’utente in merito alla
    obbligatorietà o facoltatività della firma.

9.  Acquisisce il consenso dell’utente ad apporre la firma.

10. Procede alla apposizione del sigillo elettronico qualificato (o di
    più sigilli nel caso siano previste più firme), secondo quanto
    prescritto al §4.2.

11. Propone all’utente di inviargli il documento firmato con SPID via
    posta elettronica, e/o di scaricarne una copia, e/o di
    conservarglielo e renderglielo disponibile nella propria area
    riservata in base al servizio di cui al §9.

12. Invia al SP il documento firmato con SPID con le modalità descritte
    nel §5.2.

13. Invia al SP la risposta di autenticazione della firma SPID recante
    l’esito positivo della procedura reindirizzando l’utente presso il
    SP. Nel caso in cui il punto precedente non abbia successo, l’\ IdP
    informa l’SP e l’utente in merito al mancato successo del processo
    di firma.

Il processo di cui ai punti 8 e 9 è reiterato per ogni firma.

Al termine del processo qui descritto, salvo che l’utente non abbia
scelto di avvalersi dei servizi di conservazione dei documenti firmati
(cfr. §9), l’\ IdP rimuove dai propri sistemi il documento oggetto della
sottoscrizione, nel pieno rispetto di quanto disposto dal Regolamento
GDPR.

Regole tecniche del documento sottoscritto
==========================================

Formato del documento
---------------------

Il documento predisposto dal SP per il processo di firma rispetta le
specifiche PDF versione 1.7 o successive, profilo **pdf/a-2**; inoltre
rispetta le seguenti caratteristiche tecniche:

1. il documento non richiede alcun controllo di accesso per essere
   aperto o modificato;

2. è consentita la modifica del documento almeno per quanto concerne
   l’apposizione di firme elettroniche;

3. né il contenuto del documento né i suoi metadati sono cifrati;

4. il documento è predisposto per la firma: il SP non può prevedere che
   l’\ IdP debba consentire all’utente di apportare modifiche al
   documento.

Convenzioni di nomenclatura dei documenti
-----------------------------------------

Il nome documento è costituito da tre parti obbligatorie [e una
facoltativa] variabili (indicate in *corsivo colorato*), più
l’estensione del file (in *corsivo*), più delle parti fisse (in tondo):

“\ *SPuid*\ **\_**\ *data*\ **T**\ *ora*\ **.**\ *pdf*\ ”.

In particolare:

-  *SPuid* — È un identificativo unico del SP che forma il documento. È
      una stringa costituita da un minimo di 3 e un massimo 8 caratteri
      a scelta tra i seguenti caratteri puramente alfanumerici:
      “01234567890abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ”.

-  *data* — È la data di formazione rispetto al fuso orario italiano. È
      una stringa di 8 caratteri numerici così ripartiti:

   -  quattro cifre per l’anno solare (da “2019” in poi),

   -  due cifre per il mese dell’anno (da “01” per gennaio a “12” per
      dicembre),

   -  due cifre per il giorno del mese (da “01” a “31”);

-  *ora* — È l’ora di formazione rispetto all’orario di sistema
      dell’ente federato, eventualmente *riportata al fuso orario
      italiano corrente*. È una stringa di 6 caratteri numerici così
      ripartiti:

   -  due cifre per l’ora nell’arco delle 24 ore (da “00” per la
      mezzanotte a “23”),

   -  due cifre per il minuto primo (da “01” a “59”),

   -  due cifre per il minuto secondo (da “01” a “59”);

Il nome del documento firmato con SPID resta immutato.

A titolo di esempio, il documento PDF, predisposto per la firma
dall’Agenzia per l’Italia Digitale (acronimo: “AgID”) all’ora locale
08:34:10, è “AgID_20190321T083410.pdf”.

Apposizione del q\ Seal del Service Provider
--------------------------------------------

Il SP appone il proprio q\ Seal mediante firma elettronica di tipo
pa\ d\ es, non visibile (senza alcuna componente grafica), nei formati
previsti dal Regolamento eIDAS e dalle conseguenti Decisioni di
Esecuzione (ue).

Prima di apporre il proprio q\ Seal, il SP predispone il documento
prevedendo adeguato spazio per contenere la componente grafica (o più
componenti se richiede più firme) del q\ Seal che verrà apposto
dall’\ IdP, il cui testo (cfr. §4.4) deve essere agevolmente leggibile.

Apposizione del q\ Seal dell’Identity Provider
----------------------------------------------

A completamento del processo di firma, l’\ IdP appone il proprio q\ Seal
nel documento, che è graficamente localizzato nello spazio previsto dal
SP e indicato nella richiesta di autenticazione (cfr. §5). La componente
visibile del sigillo contiene il seguente testo:

Il *%data%*, *%firmatario%* ha confermato la volonta' di apporre qui la
propria sottoscrizione ai sensi dell'art. 20, comma 1-bis, del CAD.

Dove la parte variabile *%firmatario%* è così costituita in base alla
seguente alternativa:

(a) Nel caso sia stata utilizzata un’identità digitale **non ad uso
    professionale**: il nome e cognome del firmatario (separati fra loro
    da uno spazio – esadecimale 0x20), seguiti da uno *slash* ascendente
    ‘/’ (esadecimale 0x2F) seguito dalla stringa ‘TINIT-’, seguito dal
    codice fiscale del firmatario; ad esempio: “Mario
    Rossi/TINIT-\ *RSSMR064T30H501H*\ ”.

(b) Nel caso sia stata utilizzata un’identità digitale **per uso
    professionale**: il nome e il cognome del firmatario (fra di loro
    separati da uno spazio) seguiti da uno *slash* ascendente ‘/’,
    seguiti dalla denominazione dell’organizzazione, seguita da un altro
    *slash* ascendente ‘/’, seguito da un identificativo unico
    dell’organizzazione valorizzato seguendo le alternative proposte nel
    §4.5, punto 1.a. Ad esempio, in caso di un’organizzazione dotata di
    partita iva: “\ *Mario Rossi*/Agenzia per l'Italia
    Digitale/TINIT-97735020584”.

La parte variabile *%data%* contiene la data di sottoscrizione, espressa
come una stringa di 8 caratteri numerici separati in tre gruppo da uno
*slash* ascendente ‘/’ e ripartiti come

-  due cifre per il giorno del mese (da “01” a “31”),

-  due cifre per il mese dell’anno (da “01” per gennaio a “12” per
   dicembre),

-  quattro cifre per l’anno solare (da “2019” in poi).

Il documento può contenere già una o più firme elettroniche qualificate
o sigilli elettronici qualificati, o può già essere stato oggetto di
altri processi di sottoscrizione come previsti dalle presenti Linee
guida. Il documento può richiedere più di una firma, in tal caso l’IdP
appone più sigilli.

Certificati di sigillo elettronico qualificato
----------------------------------------------

SP e IdP si dotano, presso un qtsp, di un certificato elettronico
qualificato per la creazione di sigilli elettronici. Tali certificati
sono resi disponibili nei metadata SPID.

Detti certificati qualificati sono conformi alle raccomandazioni emanate
con le *ll.gg. sui certificati elettronici* e contengono le seguenti
informazioni aggiuntive:

1. Il campo **SubjectDN**, contiene i seguenti attributi:

   a. serialNumber (oid
      `2.5.4.5 <http://http/oid-info.com/get/2.5.4.5>`__) — contiene per
      gli IdP e i SP, alternativamente, secondo il seguente ordine:

      -  la partita iva indicata con il prefisso ‘VAT’, come prescritto
            dal §5.1.4 punto 1 della norma ETSI `en
            319-\ 412-1 <http://www.etsi.org/deliver/etsi_en/319400_319499/31941201/01.01.01_60/en_31941201v010101p.pdf>`__
            (es. “VATIT-\ *1234567890*\ ”);

      -  il codice fiscale indicato con il prefisso ‘CF:’, come
            prescritto dal §5.1.4 punto 3 della suddetta norma (es.
            “CF:IT-\ *01234567890*\ ”);

      -  il numero assegnato dal Registro Imprese indicato con il
            prefisso ‘NTR’, come prescritto dal §5.1.4 punto 2 della
            suddetta norma (es. “NTRIT-\ *1234567890*\ ”)

      -  per gli SP pubblici, il codice ipa, così come risulta nel campo
            ipaEntityCode del registro SPID preceduto dal prefisso
            ‘PA:’, come prescritto dal §5.1.4 punto 3 della suddetta
            norma (es. “PA:IT-agid”).

   b. commonName (oid
      `2.5.4.3 <http://http/oid-info.com/get/2.5.4.3>`__) — contenente,
      mediante un elemento di tipo *dNSName*, il nome di dominio – privo
      di qualsiasi carattere *wildcard* – di cui al punto 5.

2. Il campo **CertificatePolicies** (oid
   `2.5.29.32 <http://oid-info.com/get/2.5.29.32>`__), contenente i
   seguenti attributi:

   c. PolicyIdentifier — valorizzato come:

      -  spidSignature (oid
            `1.3.76.16. <http://oid-info.com/get/1.3.76.16.7.1>`__\ 4.11);

   d. una limitazione d’uso indicata mediante la presenza di un campo
      userNotice (oid
      `2.5.29.49 <http://oid-info.com/get/2.5.29.49>`__), di tipo
      *explicitText*, valorizzato con il seguente testo bilingue:

..

   “Certificato usabile solo per il processo di sottoscrizione di cui
   all'art.20 del CAD/This certificate may be used only for digital
   subscription pursuant to Italian Digital Administration Code,
   art.20.”

3. keyUsage (oid `2.5.29.15 <http://oid-info.com/get/2.5.29.15>`__) —
   contiene i valori digitalSignature e keyEncipherment, cioè i bit
   :sup:`#`\ 0 e :sup:`#`\ 2, valorizzati a 1, come da specifica
   `RFC-5280 <https://tools.ietf.org/html/rfc5280>`__.

4. extendedKeyUsage (oid
   `2.5.29.16 <http://oid-info.com/get/2.5.29.16>`__) — contiene sia
   l’elemento id-kp-serverAuth (oid
   `1.3.6.1.5.5.7.3.1 <http://oid-info.com/get/1.3.6.1.5.5.7.3.1>`__)
   che l’elemento id-kp-clientAuth (oid
   `1.3.6.1.5.5.7.3.2 <http://oid-info.com/get/1.3.6.1.5.5.7.3.2>`__).

5. subjectAltName (oid
   `2.5.29.17 <http://oid-info.com/get/2.5.29.17>`__) — valorizzata con
   elemento unico di tipo *dNSName* e contenente il dominio dell’\ url
   completo (così come riportato nel registro SPID) presso il quale
   l’ente federato rende disponibile, agli enti federati della tipologia
   opposta, il servizio di trasferimento sicuro di cui al §5.2.

Richieste e risposte di autenticazione per la firma
===================================================

La **richiesta di autenticazione** per la firma SPID, introdotta al
punto 5 della procedura di cui al §3, contiene i seguenti metadati
aggiuntivi:

(a) il nome del file del documento;

(b) l’impronta dell’evidenza informatica ottenuta calcolando l’\ *hash*
       del file di cui al punto (a), calcolata dal SP ai sensi del §6;

(c) l’identificativo della funzione di *hash* crittografico utilizzato
       al punto (b);

La **risposta di autenticazione** per la firma SPID contiene
obbligatoriamente i seguenti metadati:

(d) il nome del file del documento firmato con SPID;

(e) l’impronta dell’evidenza informatica ottenuta calcolando l’\ *hash*
    del file di cui al punto (d), calcolata dall’\ IdP ai sensi del §6;

(f) l’identificativo della funzione di *hash* crittografico utilizzato
       al punto (e);

L’identificativo unico della sessione di autenticazione (*session id*)
di cui al §3 punto 3, sempre presente in ogni richiesta e risposta di
autenticazione, associa in modo univoco il documento informatico
scambiato tra SP, IdP e vice versa, ad un’unica autenticazione di firma
SPID.

La durata delle sessioni di autenticazione descritte nell’ambito del
processo di sottoscrizione di cui alle presenti Linee guida è estesa
adeguatamente per permettere lo svolgimento dell’intera procedura di
sottoscrizione.

Le richieste e risposte di autenticazione per la firma SPID seguono la
sintassi descritta nei seguenti paragrafi.

SAML
----

Le richieste e risposte di autenticazione saml contengono ciascuna
un’estensione <Signature> (*namespace* spid) contenuta nella sezione
prevista dallo standard per le estensioni saml. I metadati sopra
elencati sono realizzati mediante i seguenti elementi:

-  (a) ed (d) tramite elemento <FileName> (*namespace* spid), contenente
   il nome del file del documento, comprensivo della corretta
   estensione, composto come descritto in §4.2;

-  (b) e (e) tramite elemento <DigestValue> (*namespace* ds), contenente
   un’impronta rappresentata applicandole la trasformazione *Base64*;

-  (c) e (f) tramite elemento <DigestMethod> (*namespace* ds),
   contenente la codifica w3c della funzione di *hash* utilizzata per il
   calcolo dell’impronta del documento;

-  l’identificativo univoco di sessione è indicato nell’attributo ID
   dell’elemento <AuthnRequest> per la richiesta di autenticazione, il
   cui valore combacia con quello nell’attributo InResponseTo
   dell’elemento <Response> per la corrispondente riposta di
   autenticazione.

Qui sotto è riportato un esempio di elemento <Signature> per la
richiesta di autenticazione saml relativa a un documento in formato PDF
predisposto dall’\ SP e successivamente inviato all’\ IdP per la
sottoscrizione.

<saml2p:AuthnRequest xmlns:enc="http://www.w3.org/2001/04/xmlenc#"

*[*\ …\ *]*

Destination="https://\ *url-IdP-destinatario*"

ID="id-\ *SessionId*"

*[*\ …\ *]* >

<saml:Issuer *[*\ …\ *]*>https://\ *url-SP-inviante*\ </saml:Issuer>

*[*\ …\ *]*

<saml2p:Extensions>

<spid:Signature>

<spid:Filename>

**AgID**\ \_\ **YYYYMMDD**\ T\ **hhmmss**.pdf

</spid:Filename>

<ds:DigestMethod Algorithm="http://\ *funzione_hash*" />

<ds:DigestValue>*ImprontaDocumento\ *\ **1**\ </ds:DigestValue>

</spid:Signature>

</saml2p:Extensions>

</saml2p:AuthnRequest>

Qui sotto è riportato un esempio di elemento <Signature> per la risposta
di autenticazione saml relativa alla richiesta di autenticazione di cui
al precedente esempio, l’\ IdP comunica al IdP i metadati del documento
firmato con SPID.

<saml2p:Response xmlns:saml2p="urn:oasis:names:tc:SAML:2.0:protocol"

*[*\ …\ *]*

Destination="https://\ *url-SP-destinatario*"

ID="\_\ *ResponseID*" InResponseTo="id-\ *SessionID*"

*[*\ …\ *]* >

<saml:Issuer *[*\ …\ *]*>https://\ *url-IdP-inviante*\ </saml:Issuer>

*[*\ …\ *]*

<saml2p:Extensions>

<spid:Signature>

<spid:Filename>

**AgID**\ \_\ **YYYYMMDD**\ T\ **hhmmss**.pdf

</spid:Filename>

<ds:DigestMethod Algorithm="http://\ *funzione_hash*" />

<ds:DigestValue>*ImprontaDocumento\ *\ **2**\ </ds:DigestValue>

</spid:Signature>

</saml2p:Extensions>

</saml2p:Response>

Tutte le evidenze informatiche saml che si riferiscono al servizio in
oggetto alle presenti Linee guida indicano il riferimento urn al
*namespace* xml dell’Agenzia riservato a SPID — nel proprio elemento
radice, ovvero in tutti i singoli elementi interessati (qui
genericamente indicati come <*Element*> di *namespace* ns), come
riportato nell’esempio sotto:

<ns:*Element*

*[*\ …\ *]*

xmlns:spid="http://spid.gov.it/saml-extensions"

*[*\ …\ *]* >

*[*\ …\ *]*

</ns:*Element*>

Sistema di trasferimento sicuro dei documenti
---------------------------------------------

Ogni ente federato si dota di un sistema di trasferimento dedicato ai
documenti oggetto delle presenti Linee guida, costituito da uno storage
dedicato, un protocollo di comunicazione sicura che garantisce un
adeguato livello di confidenzialità, integrità e disponibilità, e da un
sistema di gestione dei file ricevuti.

L’interfaccia applicativa fornita dal protocollo di comunicazione per il
trasferimento di documenti dall’esterno è reso noto da ciascun ente
federato verso tutti gli enti federati, mediante l’\ url che l’ente
medesimo pubblica nel metadata SPID e il cui dominio è contestualmente
riportato nei campi commonName e subjectAltName del proprio certificato
qualificato di sigillo elettronico, di cui al §4.5, punti 1.b e 5. Tale
url indica esplicitamente il protocollo di comunicazione sicuro, i cui
dettagli sono dati in §5.2.1.

Il sistema di trasferimento è, nella sua interezza, protetto da misure
di sicurezza logica e fisica conformi almeno alle *ll.gg. sulle misure
minime di sicurezza*. Esso è inoltre adeguatamente protetto logicamente
affinché solamente gli enti federati possano trasferire file mediante
uno dei seguenti due flussi:

A. il sistema dell’\ IdP è configurato per la sola ricezione di evidenze
   informatiche provenienti dagli SP in modalità *push* (cioè con
   trasferimenti iniziati in *upstream* dal SP);

B. il sistema del SP è configurato per la sola ricezione di evidenze
   informatiche provenienti dagli IdP in modalità *push* (cioè con
   trasferimenti iniziati in *upstream* dall’\ IdP).

SP e IdP controllano che ogni file creato presso il proprio storage
soddisfi quanto prescritto nel §4.2. Non sono permessi file non conformi
a quanto prescritto.

L’\ IdP rimuove dallo storage i file ricevuti per i quali non sia
pervenuta, entro un tempo limite di **10 secondi**, una richiesta di
autenticazione proveniente dal SP.

IdP e SP verificano l’integrità dei documenti ricevuti ricalcolandone
l’impronta e confrontandola con quella contenuta, rispettivamente, nella
richiesta e nella risposta di autenticazione che le accompagnano.

IdP e SP verificano l’autenticità dei q\ Seal della controparte e
l’integrità del documento ricevuto.

Interfaccia applicativa
~~~~~~~~~~~~~~~~~~~~~~~

SP e IdP si scambiano evidenze informatiche in formato jws, in accordo
con le specifiche Open\ API su canale https, formate mediate la seguente
procedura:

1. predisposizione di una struttura json contenente sia il **dato**
   (cioè il documento oggetto di sottoscrizione) che i suoi
   **metadati**, di seguito elencati:

   a. il nome del documento da inviare, predisposto come da §4.2,

   b. l’impronta del documento da inviare sigillato elettronicamente
      come da §4.3,

   c. la funzione di *hash* impiegata al punto 1.b,

   d. la posizione ove collocare la/le componente/i grafica del q\ Seal
      (cfr. §4.4);

   e. l’eventuale obbligatorietà di ciascuna firma.

2. codifica del messaggio di cui al punto 1 in un pacchetto jwt;

3. conversione del pacchetto di cui al punto 2, mediante metodo *jws
   Compact Serialization* (cfr.
   `RFC-7515 <https://tools.ietf.org/html/rfc7515>`__), in jws con il
   sigillo elettronico qualificato.

Gli algoritmi crittografici utilizzati lungo l’intera procedura sopra
descritta sono definiti in §6. I pacchetti jws sono caratterizzati dalla
presenza degli identificativi unici di sessione (cfr. §5).

Le strutture json in base alle quali sono prodotti i pacchetti jws
scambiati durante i flussi **A** e **B** sono chiamate, rispettivamente,
pacchetto di andata e pacchetto di ritorno.

L’intestazione (*header*) comune ai pacchetti di andata e ritorno
contiene i seguenti parametri obbligatori:

-  typ — valorizzato con la stringa “JOSE”;

-  alg — valorizzato con l’identificativo jwa dell’algoritmo
   crittografico utilizzato per la firma del pacchetto jws, secondo
   quanto indicato al §6;

-  x5c — valorizzato con il certificato qualificato di sigillo
   elettronico dell’ente inviante (codificato in *Base64*, cfr.
   `RFC-4648 <https://tools.ietf.org/html/rfc4648>`__).

-  crit — valorizzato con una lista di un unico elemento “x5c”, ad
   indicare che la convalida del certificato di cui al punto precedente
   è obbligatoria.

Un esempio di intestazione sopra definita è:

{

"typ" : "JOSE",

"alg" : "ES256",

"x5c" : "*Certificato/codificato+Base64*",

"crit": ["x5c"]

}

Il *payload* dei pacchetti di andata e ritorno contiene i seguenti
parametri obbligatori:

-  jti — valorizzato con l’identificativo unico della sessione, così
   come dichiarato nella richiesta di autenticazione per firma SPID;
   epurato del prefisso “id-” – coincide con il valore che, nei
   pacchetti di andata e ritorno, si trova rispettivamente
   nell’attributo:

   -  ID dell’elemento <saml:AuthRequest> per il flusso **A** (andata),
         *ovvero*

   -  InResponseTo dell’elemento <saml:Response> per il flusso **B**
         (ritorno).

-  iss — valorizzato con l’entityId (url con schema https) dell’ente
   federato inviante; coincide con il valore dell’elemento <Issuer>;

-  aud — valorizzato con l’entityId (url con schema https) dell’ente
   federato destinatario; coincide con il valore dell’attributo
   Destination, rispettivamente, dell’elemento:

   -  <saml:AuthRequest> per il pacchetto di andata (flusso **A**),
         *ovvero*

   -  <saml:Response> per il pacchetto di ritorno (flusso **B**).

-  sub — *valorizzato solamente nel pacchetto di ritorno*, con la
   stringa *%firmatario%* identificativa del firmatario, come definita
   nel §4.4, punti (a) ovvero (b);

-  iat — valorizzato con l’orario in cui il messaggio è generato e
   inviato (rispetto al fuso orario italiano), codificato come campo
   json di tipo *NumericDate*;

-  filename — valorizzato con il nome del documento inviato; coincide
   con il valore dell’elemento <Filename> come specificato nel §4.2;

-  cty — valorizzato con la tipologia mime del documento di cui al punto
   precedente (quindi “pdf”, come da normativa
   `RFC-7515 <https://tools.ietf.org/html/rfc7515>`__);

-  payload — valorizzato con l’evidenza del documento informatico da
   trasferire, codificato in *Base64* (cfr.
   `RFC-4648 <https://tools.ietf.org/html/rfc4648>`__);

-  digest — valorizzato con una struttura json così strutturata:

   -  method — valorizzato con la codifica w3c della funzione di *hash*
         utilizzata per il calcolo dell’impronta del documento e
         coincidente con il valore dell’elemento saml <DigestMethod>,

   -  digest — valorizzato con l’impronta del documento trasferito e
         coincidente con il valore dell’elemento saml <DigestValue>;

..

   Nel pacchetto di andata:

-  signatures — valorizzato con un array json contenente tanti elementi
   quante sono le sottoscrizioni richieste; gli elementi sono strutture
   contenenti:

   -  id— valorizzato con l’identificativo univoco della firma
         nell’ambito del processo di firma;

   -  pag — valorizzato con il numero della pagina del documento ove è
         richiesto che l’\ IdP apponga la componente grafica di cui al
         §4.4;

   -  pos — contenente una struttura json con due parametri – u e v –
         ciascuno dei due valorizzati con una struttura json di due
         elementi di tipo *number*, recanti l’ascissa e la ordinata nei
         sotto-parametri x e y, rispettivamente di due vertici
         diametralmente opposti, delineanti l’area rettangolare
         definita, al §4.4, per il posizionamento della componente
         grafica del q\ Seal all’interno della pagina stessa, secondo
         quanto previsto tecnicamente per la rappresentazione di oggetti
         pdf “\ *Rectangles*\ ” secondo lo standard `iso/iec
         32000-1 <http://wwwimages.adobe.com/www.adobe.com/content/dam/acom/en/devnet/pdf/pdfs/PDF32000_2008.pdf>`__;

   -  req — booleano per indicare se la firma è facoltativa (false) o
         obbligatoria (true) per il SP richiedente. Se il firmatario non
         accetta di apporre anche solo una firma obbligatoria, l’intero
         processo di sottoscrizione termina senza successo e l’\ IdP non
         restituisce il documento al SP, informandolo della mancanza di
         volontà del firmatario.

..

   Nel pacchetto di ritorno:

-  ref— valorizzato con una array json contenente tanti elementi quante
   sono le firme richieste nel pacchetto di andata. L’elemento è una
   struttura contenente:

   -  id— valorizzato con l’identificativo univoco della firma contenuto
         nel pacchetto di andata;

   -  signed — è un booleano che conferma l’apposizione (true) o meno
         (false) della firma.

I pacchetti sono validi se conformi al presente provvedimento e a
eventuali successive indicazioni dell’Agenzia.

Seguono un esempio del pacchetto di andata e del relativo pacchetto di
ritorno per la sottoscrizione di un documento per il quale sono
richieste due firme: la prima, a pagina 3, obbligatoria; la seconda, a
pagina 7, facoltativa. Nella risposta, l’\ IdP informa il SP che
l’utente ha apposto solo la firma obbligatoria.

Esempio di pacchetto di andata:

{

"jti" : "*SessionID*",

"iss" : "https://*url-SP-inviante*",

"aud" : "https://*url-IdP-ricevente*",

"iat" : *1563235200*,

"filename" : "**AgID**\ \_\ **20190824**\ T\ **183000.\ pdf**",

"cty" : "pdf",

"digest" : {

"method" : "*schema*://*funzione_hash*",

"value" : "*ImprontaDocumento\ *\ **1**"

},

"signatures" :

[

{

"id" : "1",

"pag" : 3,

"pos" : {

"u" : { "x":89.9446, "y":719.976 },

"v" : { "x":239.978, "y":751.299 }

},

"req" : **true**

},

{

"id" : "2",

"pag" : 7,

"pos" : {

"u" : { "x":240.734, "y":686.297 },

"v" : { "x":390.768, "y":718.421 }

},

"req" : **false**

}

],

"payload" : "*BlobDocumento\ *\ **1**\ *\ +[…]+codificatoBase64*"

}

Esempio di pacchetto di ritorno:

{

"jti" : "*SessionID*",

"iss" : "https://*url-IdP-inviante*",

"aud" : "https://*url-SP-ricevente*",

"sub" : "*Mario Rossi*\ **/**\ CF:IT-\ *RSSMR064T30H501H*",

"iat" : *1563235220*,

"filename" : "**AgID**\ \_\ **20190824**\ T\ **183000.\ pdf**",

"cty" : "pdf",

"digest" : {

"method":"*schema*://*funzione_hash*",

"value" : "*ImprontaDocumento\ *\ **2**"

},

"ref" : [

{"id":"1", "signed":**true**},

{"id":"2", "signed":**false**}

],

"payload" : "*BlobDocumento\ *\ **2**\ *\ +[…]+codificatoBase64*"

}

Algoritmi crittografici
=======================

Ai fini del presente regolamento è utilizzata, per il calcolo delle
impronte, la funzione di *hash* crittografico **sha-256**, il cui
riferimento w3c è http://www.w3.org/2001/04/xmlenc#sha256.

Per la realizzazione tecnica di firme digitali (nella fattispecie, di
creazione di sigilli elettronici) è utilizzato l’algoritmo **ecdsa**
(con uso della curva ellittica p\ 256 e funzione di *hash* crittografico
sha-256), il cui riferimento w3c è
http://www.w3.org/2001/04/xmldsig-more#ecdsa-sha256 e il cui riferimento
jwa è ES256. Al di fuori del contesto dei pacchetti jwt, è usato
l’algoritmo **rsa** con lunghezza delle chiavi asimmetriche di 2048 bit
(e funzione di *hash* crittografico sha-256), il cui riferimento w3c è
http://www.w3.org/2001/04/xmldsig-more#rsa-sha256.

La versione del canale di comunicazione tls utilizzato dagli enti
federati è la 1.2 o superiore.

Gli algoritmi crittografici utilizzati per i pacchetti jws sono conformi
a quanto previsto dal presente capitolo e i loro riferimenti tecnici
sono pubblicati nella norma
`RFC-7518 <https://tools.ietf.org/html/rfc7518>`__.

Gli algoritmi e i metodi crittografici contenuti nel presente capitolo
possono essere sostituiti, rimossi o integrati con altri mediante
pubblicazione di Avvisi sul sito web istituzionale dell’Agenzia.

Codici di errore
================

In caso di errore nel processo di sottoscrizione, l’\ IdP informa
l’utente e risponde al SP con un oggetto *problem+\ json* come da norma
`RFC-7807 <https://tools.ietf.org/html/rfc7807>`__.

Gli errori sono normalizzati e pubblicati in apposita tabella
disponibile sul sito dell’Agenzia.

Tale tabella contiene:

-  Il testo normalizzato che deve essere mostrato all’utente e inserito
   nel campo detail della risposta verso il SP;

-  Il codice di risposta http.

Obblighi degli enti federati
============================

Gli enti federati sono tenuti al rispetto delle disposizioni di quanto
prescritto dal Regolamento GDPR e dal D.Lgs. N°101/2018.

Obblighi in capo agli Identity Provider
---------------------------------------

Gli IdP che offrono servizi di sottoscrizione di cui alle presenti Linee
guida, oltre a rendere disponibile ai SP il proprio servizio e
garantirne tutte le caratteristiche di confidenzialità, integrità e
disponibilità, si impegnano a non conservare né i documenti ricevuti né
i documenti firmati con SPID che sono depositati presso i propri
sistemi, rimuovendoli in modo sicuro al termine del trattamento.

Obblighi in capo ai Service Provider
------------------------------------

I SP che intendono far utilizzare la funzione di firma oggetto del
presente provvedimento, hanno l’obbligo improrogabile di consentire agli
utenti la sottoscrizione con firma elettronica qualificata.

Servizio di conservazione dei documenti firmati
===============================================

Gli IdP possono offrire ai firmatari servizi aggiuntivi di conservazione
dei documenti firmati con SPID resi accessibili all’utente attraverso
apposito servizio.

L’\ IdP è titolare del trattamento per finalità diverse da quelle del
servizio di sottoscrizione ex art. 20. L’utente è chiaramente informato
che i dati personali oggetto del servizio e i documenti firmati con SPID
sono ulteriormente trattati dall’\ IdP.

 Norme transitorie
=================

Le presenti regole tecniche sono adottate dagli enti federati di cui
alle definizioni nel §1, su base volontaria, a partire dal quindicesimo
giorno dalla data di pubblicazione della notizia della loro emanazione
sulla Gazzetta Ufficiale della Repubblica Italiana.
