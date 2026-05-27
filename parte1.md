# Compendio Integrato di Logica Proposizionale e dei Predicati

Questo documento raccoglie in modo ordinato e strutturato le formule utili, le regole di inferenza, le equivalenze logiche e gli schemi di traduzione avanzati, completi di una spiegazione teorica dettagliata per ciascuna struttura.

---

## 1. Indicatori Argomentativi e Struttura
Un argomento in logica si compone di premesse (le ragioni) e conclusioni (l'enunciato derivato). Identificarli correttamente è fondamentale per la formalizzazione:

* **Indicatori di Premessa:** Introducono i dati a supporto dell'argomentazione.
    * *Esempi:* Infatti, poiché, perché, giacché, siccome, in quanto, dato che, visto che, dal momento che, considerato che, la ragione è che.
* **Indicatori di Conclusione:** Introducono l'affermazione finale che consegue logicamente dalle premesse.
    * *Esempi:* Quindi, dunque, perciò, pertanto, così, ragion per cui, di conseguenza, stando così le cose, ne segue che, se ne deduce che, in conclusione.

---

## 2. Equivalenze Logiche Fondamentali

Le equivalenze logiche collegano formule della Logica Proposizionale (PL) e della Logica dei Predicati (QL) che condividono stabilmente gli stessi valori di verità.

| Formula Originale | Formula Equivalente | Spiegazione Teorica |
| :--- | :--- | :--- |
| $\neg(P \wedge Q)$ | $\neg P \vee \neg Q$ | **Prima Legge di De Morgan:** Negare che due enunciati siano veri insieme equivale ad affermare che almeno uno dei due è falso. |
| $(P \wedge Q)$ | $(Q \wedge P)$ | **Proprietà Commutativa:** L'ordine dei congiunti non altera il valore di verità della congiunzione. |
| $\neg(P \vee Q)$ | $\neg P \wedge \neg Q$ | **Seconda Legge di De Morgan:** Negare che sia vera almeno una tra due opzioni equivale ad affermare che sono entrambe false. |
| $(P \rightarrow Q)$ | $\neg P \vee Q$ | **Definizione del Condizionale:** Un'implicazione materiale significa semplicemente che non si dà il caso che l'antecedente sia vero e il conseguente sia falso. |
| $(P \rightarrow Q)$ | $\neg Q \rightarrow \neg P$ | **Legge di Contrapposizione:** Se il conseguente è falso, allora deve essere falso anche l'antecedente affinché il condizionale resti valido. |
| $\neg(P \rightarrow Q)$ | $P \wedge \neg Q$ | **Negazione del Condizionale:** Un condizionale è falso in un unico caso specifico: quando l'antecedente è vero e il conseguente è falso. |
| $P$ | $\neg\neg P$ | **Legge della Doppia Negazione:** Negare due volte un enunciato equivale ad affermarlo. |
| $P \wedge (Q \vee R)$ | $(P \wedge Q) \vee (P \wedge R)$ | **Legge Distributiva:** La congiunzione si distribuisce sui singoli membri di una disgiunzione. |
| $\forall x Fx$ | $\neg\exists x \neg Fx$ | Dire che una proprietà vale per *tutti* gli individui equivale a dire che *non esiste* alcun individuo che non la possieda. |
| $\exists x Fx$ | $\neg\forall x \neg Fx$ | Dire che *esiste almeno un* individuo con la proprietà $F$ equivale a negare che *tutti* gli individui ne siano privi. |
| $\forall x \neg Fx$ | $\neg\exists x Fx$ | Dire che *nessuno* possiede la proprietà $F$ equivale ad affermare che *non esiste* alcun individuo che sia $F$. |
| $\exists x \neg Fx$ | $\neg\forall x Fx$ | Dire che *esiste un elemento* privo della proprietà $F$ equivale a negare che *tutti* gli elementi siano $F$. |

---

## 3. Definizioni Semantiche e Teoria dei Modelli

* **Tautologia:** Una formula ben formata (fbf) che risulta stabilmente **vera sotto qualsiasi valutazione** o assegnazione di valori di verità (es. $P \vee \neg P$).
* **Contraddizione:** Una formula ben formata che risulta stabilmente **falsa in ogni possibile valutazione** (es. $P \wedge \neg P$).
* **Contingente:** Una formula il cui valore di verità non è costante: risulta vera in alcune valutazioni e falsa in altre (es. $P \rightarrow Q$).
* **Argomento Corretto (Sound):** Un argomento che, oltre a essere logicamente valido (la verità delle premesse garantisce la verità della conclusione), possiede premesse che sono **effettivamente vere nel mondo reale**.
* **Decidibile:** Una logica per la quale esiste un algoritmo meccanico effettivo in grado di stabilire, in un numero finito di passi, se una formula qualsiasi sia valida o meno. (La logica proposizionale è decidibile tramite tavole di verità; la logica dei predicati non lo è).
* **Correttezza (Soundness sintattica):** Se $\Gamma \vdash \varphi$ allora $\Gamma \models \varphi$. Garantisce che il sistema deduttivo sia affidabile: se una formula è dimostrabile formalmente tramite regole sintattiche, allora è anche semanticamente vera in tutti i modelli.
* **Completezza:** Se $\Gamma \models \varphi$ allora $\Gamma \vdash \varphi$. Garantisce che il sistema sia potente: tutte le verità logiche (valide semanticamente) possiedono una via di dimostrazione formale all'interno del calcolo sintattico.

---

## 4. Alberi Semantici (Regole di Espansione)

Gli alberi semantici verificano la consistenza di un insieme di formule cercando un controesempio. Se tutti i rami si chiudono incontrando una contraddizione esplicita ($P$ e $\neg P$), la formula analizzata (o la negazione della conclusione) è inconsistente.

> ⚠️ **Ordine strategico di espansione (Priorità per evitare rami complessi):**
> 1. Regole che non ramificano (sviluppo in colonna).
> 2. Regole Esistenziali ($\exists$) $\rightarrow$ *Richiedono l'introduzione di una costante individuali completamente nuova.*
> 3. Regole che ramificano (apertura di percorsi alternativi).
> 4. Regole Universali ($\forall$) $\rightarrow$ *Si applicano e riapplicano su tutte le costanti note nel ramo.*

### Meccanismi di Sviluppo dei Nodi:
* **Doppia Negazione:** Da $\neg\neg P$ si ricava direttamente $P$ (sviluppo lineare).
* **Congiunzione ($P \wedge Q$):** Non ramifica. Si trascrivono le fbf componenti $P$ e $Q$ l'una sotto l'altro sullo stesso percorso.
* **Disgiunzione ($P \vee Q$):** Ramifica. L'albero si sdoppia in due percorsi paralleli: il ramo sinistro esplora lo scenario in cui è vera $P$, il ramo destro lo scenario in cui è vera $Q$.
* **Condizionale ($P \rightarrow Q$):** Ramifica. Si scompone nell'alternativa logica: o è falso l'antecedente ($\neg P$) o è vero il conseguente ($Q$).
* **Condizionale Negato ($\neg(P \rightarrow Q)$):** Non ramifica. Rappresenta l'unico caso di falsità dell'implicazione: si trascrivono in colonna l'antecedente vero ($P$) e il conseguente falso ($\neg Q$).
* **Bicondizionale ($P \leftrightarrow Q$):** Ramifica in due coppie. Rappresenta la richiesta di equivalenza: o sono veri entrambi $[P, Q]$ (ramo sinistro) o sono falsi entrambi $[\neg P, \neg Q]$ (ramo destro).
* **Esistenziale ($\exists x P(x)$):** Si istanzia la proprietà eliminando il quantificatore e sostituendo la variabile $x$ con un nome di costante (es. $c$) che **non deve essere mai apparso prima** nel ramo corrente.
* **Universale ($\forall x P(x)$):** Si istanzia la proprietà su una costante esistente o su un termine generico. La regola resta attiva e riutilizzabile se vengono introdotte nuove costanti successivamente.
* **Identità Negata ($\neg x = y$):** Viene assimilata a una fbf complessa di tipo $\neg(x=y)$. Genera la chiusura del ramo ($\times$) se nello stesso tracciato compare l'affermazione diretta di identità $x=y$.

---

## 5. Deduzione Naturale

### Regole di Eliminazione e Introduzione Proposizionale
* **$\wedge E$ (Eliminazione Congiunzione):** Da una congiunzione solida $P \wedge Q$ è lecito estrarre e isolare uno qualsiasi dei due componenti ($P$ oppure $Q$).
* **$\vee I$ (Introduzione Disgiunzione):** Data una formula vera $P$, è sintatticamente valido indebolirla inserendola in una qualsiasi disgiunzione ($P \vee Q$).
* **$\rightarrow E$ (Modus Ponens / Eliminazione Condizionale):** Avendo a disposizione un condizionale $P \rightarrow Q$ e l'affermazione del suo antecedente $P$, si estrae e conclude il conseguente $Q$.
* **$\neg E$ (Eliminazione Negazione):** Consente di rimuovere due negazioni consecutive ($\neg\neg P$) tornando all'affermazione atomica $P$.

### Vincoli Rigidi sui Quantificatori (Sintassi)
* **$\forall E$ (Eliminazione Universale):** Da una legge generale $\forall x Fx$ si deduce la sua applicazione su un individuo specifico $Fa$. Non ha vincoli: la costante può essere un termine vecchio o nuovo.
* **$\forall I$ (Introduzione Universale):** Permette di generalizzare un'osservazione da $Fa$ a $\forall x Fx$. **Vincolo tassativo:** La costante $a$ utilizzata deve essere *arbitraria*, il che significa che non deve comparire all'interno di ipotesi o assunzioni temporanee ancora aperte e non scaricate.
* **$\exists I$ (Introduzione Esistenziale):** Da un caso particolare $Fa$ si passa all'affermazione esistenziale $\exists x Fx$. Non presenta vincoli restrittivi.
* **$\exists E$ (Eliminazione Esistenziale):** Di fronte a una premessa esistenziale $\exists x Fx$, si apre un'ipotesi assumendo un caso esemplificativo $Fa$. **Vincolo tassativo:** La costante $a$ deve essere **rigorosamente nuova**; non può comparire né nella premessa esistenziale, né nella conclusione finale del teorema, né in altre assunzioni attive nel sistema.

---

## 6. Schemi Pratici di Traduzione d'Esame

### Forme Quantificate Standard (Quadrato Aristotelico)
* *Tutti i P sono Q (Universale Affermativa):*
    $$\forall x (Px \rightarrow Qx)$$
    *Spiegazione:* Per qualsiasi individuo, se possiede la proprietà $P$, allora possiede necessariamente anche la proprietà $Q$.
* *Alcuni P sono Q (Esistenziale Affermativa):*
    $$\exists x (Px \wedge Qx)$$
    *Spiegazione:* Esiste almeno un individuo nel dominio che possiede contemporaneamente sia la proprietà $P$ sia la proprietà $Q$.
* *Nessun P è Q (Universale Negativa):*
    $$\forall x (Px \rightarrow \neg Qx)$$
    *Spiegazione:* Per ogni individuo, se è un $P$, allora non è un $Q$ (le due proprietà si escludono reciprocamente).
* *Non tutti i P sono Q (Esistenziale Negativa):*
    $$\exists x (Px \wedge \neg Qx)$$
    *Spiegazione:* Esiste almeno un individuo che è caratterizzato da $P$ ma che risulta privo della proprietà $Q$.

### Formalizzazioni Avanzate (Identità e Limitazioni Numeriche)
* *Solo a è un P (Esclusività singola):*
    $$\forall x (Px \leftrightarrow x=a)$$
    *Spiegazione:* Un individuo possiede la proprietà $P$ se e solo se quell'individuo è esattamente l'oggetto $a$.
* *Solo Alice ($a$) e Bruno ($b$) sono P (Esclusività plurale):*
    $$\forall x (Px \leftrightarrow (x=a \vee x=b))$$
    *Spiegazione:* Gli unici elementi che soddisfano il predicato $P$ sono l'oggetto $a$ e l'oggetto $b$.
* *Tutti i P tranne a sono Q (Eccezione):*
    $$Pa \wedge \neg Qa \wedge \forall x ((Px \wedge x \neq a) \rightarrow Qx)$$
    *Spiegazione:* L'oggetto $a$ è un $P$ ma non è un $Q$, mentre per tutti gli altri individui, se sono $P$, allora sono anche $Q$.
* *C'è esattamente un P (Esistenza e Unicità):*
    $$\exists x (Px \wedge \forall y (Py \rightarrow y=x))$$
    *Spiegazione:* Esiste un individuo $x$ che è $P$, e qualunque altro individuo $y$ che sia $P$ deve coincidere necessariamente con $x$.
* *Esistono almeno due P:*
    $$\exists x \exists y (Px \wedge Py \wedge x \neq y)$$
    *Spiegazione:* Si possono trovare nel dominio almeno due individui distinti che condividono la proprietà $P$.
* *C'è al massimo un P:*
    $$\forall x \forall y ((Px \wedge Py) \rightarrow x=y)$$
    *Spiegazione:* Se si trovano due individui che hanno la proprietà $P$, si scoprirà che in realtà si tratta dello stesso identico oggetto.
* *Ci sono al massimo due P:*
    $$\forall x \forall y \forall z ((Px \wedge Py \wedge Pz) \rightarrow (x=y \vee x=z \vee y=z))$$
    *Spiegazione:* Presi tre elementi qualsiasi del dominio che siano $P$, almeno due di essi devono essere identici tra loro (impedendo la presenza di un terzo elemento distinto).
* *Alice ride ($R$) solo se Bruno scherza ($S$):*
    $$R \rightarrow S$$
    *Spiegazione:* Lo scherzo di Bruno è condizione necessaria per la risata di Alice. Se Alice ride, allora Bruno sta scherzando.

### Logica del Secondo Ordine (Quantificazione su Proprietà)
* *Esiste una proprietà X che tutti i P hanno:*
    $$\exists X \forall x (Px \rightarrow Xx)$$
    *Spiegazione:* Si quantifica sopra i predicati. Esiste un concetto o proprietà $X$ tale che ogni elemento che rientra in $P$ possiede anche $X$.
* *Principio di Identità degli Indiscernibili (Leibniz):*
    $$\forall x \forall y (x=y \leftrightarrow \forall X (Xx \leftrightarrow Xy))$$
    *Spiegazione:* Due entità individuali $x$ e $y$ sono identiche se e solo se condividono precisamente ogni singola proprietà astratta $X$.
