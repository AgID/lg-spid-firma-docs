.. _`§7`:

Codici di ritorno applicativo
=============================

.. highlights:

   Elenco dei messaggi di stato (ed errrore) restituiti al termine della procedura.

Possono presentarsi errori in due fasi distinte del processo di sottoscrizione:

 1. durante l’autenticazione SAML per la firma cn SPID di cui al §\ :ref:`5.1 <§5.1>`; ovvero
 
 2. durante il trasferimento sicuro dei documenti di cui al §\ :ref:`5.2 <§5.2>`.

Nel primo caso, gli errori sono notificati dall’IdP al SP con la risposta di autenticazione
(secondo quanto previsto dal protocollo SAML). Contestualmente, l’utente è visivamente
notificato dell’errore presso l’interfaccia dell’IDP.

La :ref:`Tabella 1 <tabella01>` qui sotto elenca soltanto gli errori specifici alla procedura di
sottoscrizione, potendo venire notificati anche quelli già previsti dalle Regole Tecniche
SPID e pubblicati, nel documento
`SPID – Tabella messaggi di anomalie <https://www.agid.gov.it/sites/default/files/repository_files/regole_tecniche/spid-messaggi.pdf>`_, presso il sito web dell’Agenzia.

.. table:: Errori specifici per la procedura di sottoscrizione.
   :name: tabella01
   
   +-----+---------------------------------------------------------------+------------------------------+------------------+----------------------------------------------------+--------------+---------------+
   | #   | scenario                                                      | binding                      | HTTP Status Code | SAML Status Code / sub-Status / Status Message     | destinatario | schermata IdP |
   +=====+===============================================================+==============================+==================+====================================================+==============+===============+
   | 771 | L’utente ha negato il consenso ad apporre firme obbligatorie. | HTTP *POST* /                | n.a.             | ``urn:oasis:names:tc:SAML:2.0:status:Responder``   | SP           | n.a.          |
   |     |                                                               | *HTTP Redirect*              |                  | ``urn:oasis:names:tc:SAML:2.0:status:AuthnFailed`` |              |               |
   |     |                                                               |                              |                  | :code:`ErrorCode nr771`                            |              |               |
   +-----+---------------------------------------------------------------+------------------------------+------------------+----------------------------------------------------+--------------+---------------+
   | 772 | Il documento non è disponibile.                               | HTTP *POST* /                | n.a.             | ``urn:oasis:names:tc:SAML:2.0:status:Responder``   | SP           | n.a.          |
   |     |                                                               | *HTTP Redirect*              |                  | ``urn:oasis:names:tc:SAML:2.0:status:AuthnFailed`` |              |               |
   |     |                                                               |                              |                  | :code:`ErrorCode nr772`                            |              |               |
   +-----+---------------------------------------------------------------+------------------------------+------------------+----------------------------------------------------+--------------+---------------+

Nel secondo caso, il mittente del documento è informato dal destinatario secondo le indicazioni
della norma :RFC:`7807`. Il mittente, ricevuto il messaggio di errore, lo notifica all’utente.

La :ref:`Tabella 2 <tabella02>` elenca i possibili codici di ritorno, veicolati nel pacchetto JWT contenente
un oggetto di *Content-Type* ``problem+json``.
.. table:: Codici di ritorno del sistema di trasferimento sicuro dei documenti.
   :name: tabella02
   
   +-----+---------------------------------------------------------------+------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+--------------+---------------+
   | #   | scenario                                                      | binding                      | HTTP Status Code | SAML Status Code / sub-Status / Status Message                                                                                  | destinatario | schermata IdP |
   +=====+===============================================================+==============================+==================+=================================================================================================================================+==============+===============+
   | 771 | L’utente ha negato il consenso ad apporre firme obbligatorie. | HTTP *POST*, *HTTP Redirect* | n.a.             | ``urn:oasis:names:tc:SAML:2.0:status:Responder`` / ``urn:oasis:names:tc:SAML:2.0:status:AuthnFailed`` / :code:`ErrorCode nr771` | SP           | n.a.          |
   +-----+---------------------------------------------------------------+------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+--------------+---------------+
   | 772 | Il documento non è disponibile.                               | HTTP *POST*, *HTTP Redirect* | n.a.             | ``urn:oasis:names:tc:SAML:2.0:status:Responder`` / ``urn:oasis:names:tc:SAML:2.0:status:AuthnFailed`` / :code:`ErrorCode nr772` | SP           | n.a.          |
   +-----+---------------------------------------------------------------+------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+--------------+---------------+


d
.. forum_italia::
   :topic_id: 12097
   :scope: document
