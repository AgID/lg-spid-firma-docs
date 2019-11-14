.. _`§7`:

Codici di errore
================

.. highlights:

   Elenco dei messaggi di stato (ed errrore) restituiti al termine della procedura.

Possono presentarsi errori in due fasi distinte del processo di sottoscrizione:

 1. durante l'autenticazione SAML per la firma cn SPID di cui al §\ :ref:`5.1 <§5.1>`; ovvero
 
 2. durante il trasferimento sicuro dei documenti di cui al §\ :ref:`5.2 <§5.2>`.

Nel primo caso, gli errori sono notificati dall’IdP al SP con la risposta di autenticazione
(secondo quanto previsto dal protocollo SAML). Contestualmente, l’utente è visivamente
notificato dell’errore presso l’interfaccia dell’IDP.

La Tabella 1 qui sotto elenca soltanto gli errori specifici alla procedura di sottoscrizione,
potendo venire notificati anche quelli già previsti dalle Regole Tecniche SPID e pubblicati,
nel documento :ref:`SPID – Tabella messaggi di anomalie <https://www.agid.gov.it/sites/default/files/repository_files/regole_tecniche/spid-messaggi.pdf>`,
presso il sito web dell’Agenzia.

Nel secondo caso, il mittente del documento è informato dal destinatario secondo le indicazioni
della norma :RFC:`7807`. Il mittente, ricevuto il messaggio di errore, lo notifica all’utente.

La Tabella 2 elenca i possibili errori, veicolati nel pacchetto JWT contenente un oggetto di
*Content-Type* ``problem+json``.

.. forum_italia::
   :topic_id: 6
   :scope: document
