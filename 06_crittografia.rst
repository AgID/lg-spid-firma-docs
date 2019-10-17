Algoritmi crittografici
=======================

Ai fini del presente regolamento è utilizzata, per il calcolo delle
impronte, la funzione di *hash* crittografico **SHA-256**, il cui
riferimento W3C è http://www.w3.org/2001/04/xmlenc#sha256.

15. Per la realizzazione tecnica di firme digitali (nella fattispecie,
    di creazione di sigilli elettronici) è utilizzato l’algoritmo
    **ECDSA** (con uso della curva ellittica P256 e funzione di *hash*
    crittografico SHA-256), il cui riferimento W3C è
    http://www.w3.org/2001/04/xmldsig-more#ecdsa-sha256 e il cui
    riferimento JWA è ``ES256``. Al di fuori del contesto dei pacchetti
    JWT, è usato l’algoritmo **RSA** con lunghezza delle chiavi
    asimmetriche di 2048 bit (e funzione di *hash* crittografico
    SHA-256), il cui riferimento W3C è
    http://www.w3.org/2001/04/xmldsig-more#rsa-sha256.

16. Il canale di comunicazione utilizzato dagli enti federati utilizza
    per l’autenticazione e la confidenzialità l’algoritmo TLS alla
    versione 1.2 o superiore.

17. Gli algoritmi crittografici utilizzati per i pacchetti JWS sono
    conformi a quanto previsto dal presente capitolo e i loro
    riferimenti tecnici sono pubblicati nella norma
    `RFC-7518 <https://tools.ietf.org/html/rfc7518>`__.

18. Gli algoritmi e i metodi crittografici contenuti nel presente
    capitolo possono essere sostituiti, rimossi o integrati con altri
    mediante pubblicazione di Avvisi sul sito web istituzionale
    dell’Agenzia.
