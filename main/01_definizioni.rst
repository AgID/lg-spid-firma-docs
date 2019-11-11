.. _`§1`:

Definizioni
===========

Ai fini delle presenti Linee guida, oltre ad applicarsi le definizioni di cui all’articolo 1 del CAD,
e del DPCM 24 ottobre 2014 *Definizione delle caratteristiche del sistema pubblico per la gestione dell'identità digitale di cittadini e imprese (SPID)*, si intende per:

.. _`AgID`:
-  **Agenzia** o **AgID**: Agenzia per l’Italia Digitale;

.. _`CAD`:
-  **CAD**: `D.Lgs. 7 marzo 2005 №82 <https://docs.italia.it/italia/piano-triennale-ict/codice-amministrazione-digitale-docs/it/v2018-09-28/>`__, *Codice dell’Amministrazione Digitale*, e sue successive modificazioni;

-  **documento firmato con SPID**: il documento sottoscritto ai sensi delle presenti Linee guida;

-  **documento predisposto per la firma**: il documento preparato dal SP per essere sottoscritto ai sensi delle presenti Linee guida;

-  **ente federato**: gestore di identità digitali ovvero fornitore di servizi della federazione SPID;

-  **firma**: vedi sottoscrizione;

-  **firmatario**: la persona fisica che, utilizzando la propria identità digitale SPID di livello 2 o superiore, conferisce al documento informatico il valore e l’efficacia previsti dall’articolo 20 del CAD attraverso il processo di firma di cui al presente provvedimento;

.. _`hash`:
-  **impronta**: impronta crittografica, risultante dell’applicazione di una funzione di hash crittografica a un’evidenza informatica;

.. _`payload`:
-  **evidenza informatica**: sequenza finita di bit che può essere elaborata da una procedura informatica;

.. _`llgg uso_professionale`:
-  **LL.GG. identità digitali ad uso professionale**: *Linee guida per il rilascio dell’identità digitale per uso professionale*, pubblicate con `Determinazione AgID №318/2019 <https://www.agid.gov.it/sites/default/files/repository_files/linee_guida_identita_digitale_per_uso_professionale_v.1.0.pdf>`__ e successive modificazioni;

.. _`llgg certificati`:
-  **LL.GG. sui certificati elettronici**: *Linee guida contenenti Regole Tecniche e Raccomandazioni afferenti la generazione di certificati elettronici qualificati, firme e sigilli elettronici qualificati e validazioni temporali elettroniche qualificate*, pubblicate con `Determinazione AgID №121/2019 <http://www.agid.gov.it/sites/default/files/repository_files/regole_e_raccomandazioni_v1.1.pdf>`__ e successive modificazioni;

.. _`llgg mis min sicurezza`:
-  **LL.GG. sulle misure minime di sicurezza**: `Circolare AgID №1/2017 <https://www.agid.gov.it/it/sicurezza/misure-minime-sicurezza-ict>`__ e successive modificazioni, recante *Misure minime di sicurezza ICT per le pubbliche amministrazioni*;

.. _`registro SPID`:
-  **registro SPID**: elenco dei soggetti appartenenti alla federazione SPID, previsto dalla vigente normativa e disponibile all'URL https://registry.spid.gov.it;

.. _`eIDAS`:
-  **Regolamento eIDAS**: Regolamento (UE) №910/2014 del Parlamento Europeo e del Consiglio, del 23 luglio 2014, in materia di identificazione elettronica e servizi fiduciari per le transazioni elettroniche nel mercato interno e che abroga la direttiva 1999/93/CE;

.. _`GDPR`:
-  **Regolamento GDPR**: Regolamento (UE) №679/2016 del Parlamento Europeo e del Consiglio, del 27 aprile 2016, relativo alla protezione delle persone fisiche con riguardo al trattamento dei dati personali, nonché alla libera circolazione di tali dati e che abroga la direttiva 95/46/CE;

-  **richiesta di autenticazione**: l’evidenza informatica con la quale un SP richiede l’avvio di una sessione di autenticazione presso un IdP (cioè l’\ *authentication request*);

-  **risposta di autenticazione**: l’evidenza informatica con la quale un IdP comunica i dati personali, o il diniego a fornirli, presso un SP (*response*);

-  **sottoscrizione**: il processo di cui all’articolo 20, comma 1-bis del CAD;

-  **titolare della piattaforma**: il soggetto pubblico o privato che, in qualità di SP, rende possibile a un firmatario la formazione di un documento informatico per via telematica, al fine di conferirgli il valore e l’efficacia previsti dall’articolo 20 del CAD.

Sono anche utilizzati i seguenti acronimi o abbreviazioni:

.. _`API`:
-  **API**: interfaccia applicativa (*application programming interface*);

.. _`IdP`:
-  **IdP**: gestore di identità digitali nel contesto della federazione SPID;

.. _`JSON`:
-  **JSON**: *JavaScript Object Notation*, come previsto dalla norma :RFC:`8259`;

.. _`JWA`:
-  **JWA**: algoritmi crittografici JSON (*JSON Web Algorithm*), come previsto dalla norma :RFC:`7518`;

.. _`JWS`:
-  **JWS**: pacchetto JWT firmato (*JSON Token Signature*), come previsto dalla norma :RFC:`7515`;

.. _`JWT`:
-  **JWT**: pacchetto JSON per applicazioni web (*JSON Web Token*), come previsto dalla norma :RFC:`7797`;

.. _`QSeal`:
-  **QSeal**: sigillo elettronico qualificato, come da regolamento eIDAS;

.. _`QTSP`:
-  **QTSP**: prestatore di servizi fiduciari elettronici qualificati, come da Regolamento eIDAS;

.. _`SAML`:
-  **SAML**: `Security Assertion Markup Language <http://docs.oasis-open.org/security/saml/v2.0/saml-2.0-os.zip>`__,
   versione 2.0, pubblicato da OASIS;

.. _`SP`:
-  **SP**: fornitore di servizi nella federazione SPID, ovvero *service provider* nel contesto SAML, ovvero *relying party* nel contesto OIDC;

.. _`SPID`:
-  **SPID**: il Sistema Pubblico di Identità Digitale, introdotto con il DPCM del 24 ottobre 2014, pubblicato sulla *G.U.* Serie Generale №285 del 9 dicembre 2014.


.. forum_italia::
   :topic_id: 6
   :scope: document
