.. _`§5`:

Richieste e risposte di autenticazione per la firma
===================================================

.. highlights:

   Sintassi dei messaggi SAML e JWT scambiati tra IdP e SP
   come parte del processo di autenticazione e di sottoscrizione.

La **richiesta di autenticazione** per la firma SPID, introdotta al
punto 4 della procedura di cui al §\ :ref:`3 <§3>`, contiene i seguenti metadati
aggiuntivi:

a. il nome del file del documento predisposto per la firma;

b. l’impronta dell’evidenza informatica ottenuta calcolando l’\ :ref:`hash <hash>`
   del file di cui al punto a, calcolata dal SP conformemente a quanto
   indicato al §\ :ref:`6 <§6>`;

c. l’identificativo della funzione di *hash* crittografico utilizzato al
   punto b;

d. il codice fiscale del soggetto che deve apporre la firma.

La **risposta di autenticazione** per la firma SPID contiene
obbligatoriamente i seguenti metadati:

e. il nome del file del documento firmato con SPID;

f. l’impronta dell’evidenza informatica ottenuta calcolando l’\ :ref:`hash <hash>`
   del file di cui al punto e, calcolata dall’IdP conformemente a quanto
   indicato al §\ :ref:`6 <§6>`;

g. l’identificativo della funzione di *hash* crittografico utilizzato al
   punto f.

L’identificativo unico della sessione di autenticazione (*session ID*),
sempre presente in ogni richiesta e risposta di autenticazione, associa
in modo univoco il documento informatico scambiato tra SP, IdP e vice
versa, ad un’unica autenticazione di firma con SPID.

La durata delle sessioni di autenticazione descritte nell’ambito del
processo di sottoscrizione di cui alle presenti Linee guida è estesa
adeguatamente per permettere lo svolgimento dell’intera procedura di
sottoscrizione.

Le richieste e risposte di autenticazione per la firma SPID seguono la
sintassi descritta nei seguenti paragrafi.

.. toctree::
  :maxdepth: 3

  05/05.1_saml.rst
  05/05.2_secure-dataio.rst


.. forum_italia::
   :topic_id: 6
   :scope: document
