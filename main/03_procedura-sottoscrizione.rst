.. _`§3`:

Procedura di sottoscrizione ex articolo 20 comma 1-bis del CAD
===============================================================

.. highlights:

Descrizione passo-passo dell'intera procedura di sottoscrizione tramite SPID.

Il processo di cui all’articolo 20 comma 1\ *-bis* del :ref:`CAD <CAD>` non può essere
adoperato utilizzando identità digitali SPID per persona giuridica;
possono essere utilizzate esclusivamente le identità digitali della
persona fisica e le identità digitali per uso professionale.

Tutti i SP interessati hanno il diritto di avvalersi del servizio in oggetto.

I metadati SPID indicano se l’IdP offre il servizio in oggetto.

Se l'IdP offre il servizio in oggetto, il relativo metadata contiene l'elemento :code:`<SignatureArt20>` valorizzato con il valore ``true`` come estensione all'interno dell'elemento :code:`EntityDescriptor` (vedi esempio). Nel caso in cui l'elemento :code:`<SignatureArt20>` sia presente ma valorizzato con ``false``, è da intendersi che l'IdP *non* offre il servizio.

.. code-block:: xml

 <EntityDescriptor>
     <ds:Signature> ... </ds:Signature>
     <IDPSSODescriptor> ... </IDPSSODescriptor>
     <Extensions>
         <spid:SignatureArt20>true</spid:SignatureArt20>
     </Extensions>
     <Organization> ... </Organization>
 </EntityDescriptor>

Il servizio di sottoscrizione oggetto delle presenti Linee guida è
realizzato per permettere al medesimo utente di sottoscrivere una o più
parti del medesimo documento, attraverso un’unica sessione di
autenticazione SPID e, al contempo, a utenti distinti di sottoscrivere
il medesimo documento, in tempi e con sessioni di autenticazione SPID
distinte.

Il processo di firma prevede che l’utente, tramite il SP, esegua un
processo di autenticazione al fine della firma, con la propria identità
digitale di livello 2 o superiore, scegliendo il proprio IdP. Per la
scelta dell’IdP, il SP mostra il consueto bottone “*Entra con SPID*”,
contenente i soli IdP che offrono tale servizio.

.. toctree::
  :maxdepth: 3

  03/03.1_predisposizione-doc.rst
  03/03.2_consenso-sottoscrizione.rst

.. discourse::

:topic_identifier: 666
