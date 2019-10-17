Richieste e risposte di autenticazione per la firma
===================================================

La **richiesta di autenticazione** per la firma SPID, introdotta al
punto 5 della procedura di cui al §3, contiene i seguenti metadati
aggiuntivi:

1. il nome del file del documento;

2. l’impronta dell’evidenza informatica ottenuta calcolando l’\ *hash*
   del file di cui al punto 1;

3. l’identificativo della funzione di *hash* crittografico utilizzato al
   punto 2.

La **risposta di autenticazione** per la firma SPID contiene
obbligatoriamente i seguenti metadati:

4. il nome del file del documento firmato con SPID

5. l’impronta dell’evidenza ottenuta calcolando l’\ *hash* del file di
   cui al punto 4, calcolata dall’IdP ai sensi del §6;

6. l’identificativo della funzione di *hash* crittografico utilizzato al
   punto 5.

L’identificativo unico della sessione di autenticazione (*session ID*)
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

.. toctree::
  :maxdepth: 3
  :caption: Indice dei contenuti

  05_authreq-response/saml.rst
  05_authreq-response/sistema-di-trasferimento-sicuro-dei-documenti.rst
