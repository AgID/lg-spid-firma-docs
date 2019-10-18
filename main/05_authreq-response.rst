Richieste e risposte di autenticazione per la firma
===================================================

.. highlights:

   Sintassi dei messaggi SAML e JWT scambiati tra IdP e SP
   come parte del processo di autenticazione e di sottoscrizione.

La **richiesta di autenticazione** per la firma :ref:`SPID`, introdotta al
punto 5 della procedura di cui al §3, contiene i seguenti metadati
aggiuntivi:

1. il nome del file del documento;

2. l’impronta dell’evidenza informatica ottenuta calcolando l’:ref:`impronta <hash>`
   del file di cui al punto 1;

3. l’identificativo della funzione di *hash* crittografico utilizzato al
   punto 2.

La **risposta di autenticazione** per la firma :ref:`SPID` contiene
obbligatoriamente i seguenti metadati:

4. il nome del file del documento firmato con :ref:`SPID`;

5. l’impronta dell’evidenza ottenuta calcolando l’:ref:`impronta <hash>` del file di
   cui al punto 4, calcolata dall’:ref:`IdP` ai sensi del §6;

6. l’identificativo della funzione di *hash* crittografico utilizzato al
   punto 5.

L’identificativo unico della sessione di autenticazione (*session ID*)
di cui al §3 punto 3, sempre presente in ogni richiesta e risposta di
autenticazione, associa in modo univoco il documento informatico
scambiato tra :ref:`SP`, :ref:`IdP` e vice versa, ad un’unica autenticazione di firma
:ref:`SPID`.

La durata delle sessioni di autenticazione descritte nell’ambito del
processo di sottoscrizione di cui alle presenti Linee guida è estesa
adeguatamente per permettere lo svolgimento dell’intera procedura di
sottoscrizione.

Le richieste e risposte di autenticazione per la firma :ref:`SPID` seguono la
sintassi descritta nei seguenti paragrafi.

.. toctree::
  :maxdepth: 3

  05/05.1_saml.rst
  05/05.2_secure-dataio.rst

.. discourse::

:topic_identifier: 666
