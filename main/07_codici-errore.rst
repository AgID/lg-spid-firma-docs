.. _`§7`:

Codici di ritorno applicativo
=============================

Possono presentarsi errori in due fasi distinte del processo di sottoscrizione:

 1. durante l’autenticazione :ref:`SAML <SAML>` per la firma con SPID di cui al §\ :ref:`5.1 <§5.1>`; ovvero
 
 2. durante il trasferimento sicuro dei documenti di cui al §\ :ref:`5.2 <§5.2>`.

Nel primo caso, gli errori sono notificati dall’IdP al SP con la risposta di autenticazione
(secondo quanto previsto dal protocollo SAML). Contestualmente, l’utente è visivamente
notificato dell’errore presso l’interfaccia dell’IdP.

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
   
   ================  ====  =================================  =================================================================================================
   HTTP Status Code  code  title                              detail                                                                                           
   ================  ====  =================================  =================================================================================================
   201                     *created*                          Errore nella richiesta: Pacchetto malformato.                                                    
   400               1     JWS malformato                     Errore nella richiesta: Pacchetto malformato.                                                    
   400               2     nome del file invalido             Errore nella richiesta: Nome del file non valido.                                                
   400               3     file corrotto                      Errore nella richiesta: Documento corrotto.                                                      
   400               4     documento malformato               Errore nella richiesta: Documento malformato.                                                    
   400               5     formato del file invalido          Errore nella richiesta: Formato del file non previsto.                                           
   400               6     *hash* del documento non corretto  Errore nella richiesta: L’impronta crittografica del file non corrisponde con quella dichiarata. 
   401                     QSeal invalido                     Errore nella richiesta: Certificato di sigillo elettronico non valido.                           
   503                     servizio non disponibile           Servizio temporaneamente non disponibile.                                                        
   ================  ====  =================================  =================================================================================================

