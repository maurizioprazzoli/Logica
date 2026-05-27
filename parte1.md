# Compendio Integrato di Logica Proposizionale e dei Predicati

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

# Appunti di Logica (PL e QL)

## Concetti Fondamentali

* **Forma valida:** Tutte le esemplificazioni dell'argomento sono valide.
* **Argomento valido:** Almeno una forma dell'argomento è valida (es. $P \rightarrow Q, P \vdash Q$).
* **Argomento Logicamente valido:** La validità dipende esclusivamente dal significato delle costanti logiche presenti in PL e QL.
  * *Esempio:* $Fa \vdash \exists x Fx$
  * *Nota:* Non dipende da termini non logici come "primo", "Superman", "più alto di".
  * *Nota:* Se Argomento Logicamente valido allora Argomento valido.
* **Argomento Tautologicamente valido (PL):** La validità dipende solo dal significato delle costanti logiche in PL.
  * *Esempio:* $P \wedge Q \vdash P$
  * *Nota:* Non dipende da concetti atomici o predicati come "primo" o "Superman".
  * *Nota:* Se Argomento Tautologicamente valido allora Argomento Logicamente valido.
* **Corretto (Sound):** L'argomento è formalmente valido **e** le sue premesse sono tutte vere nel mondo attuale.
  * *Esempio:* Tutti gli uomini sono mortali. Socrate è un uomo. Dunque Socrate è mortale.
* **Forma argomentativa:** Uno schema astratto ottenuto sostituendo gli enunciati con variabili logiche (es. $P \rightarrow Q, P \vdash Q$).
* **Esemplificazione:** Un argomento concreto ottenuto sostituendo le variabili logiche con enunciati reali.
  * *Esempio:* "Se piove mi bagno. Piove. Quindi mi bagno."

---

## Tipologie di Fbf (Formule Ben Formate)

> **Fbf:** Formula ben formata che segue le regole sintattiche della logica.

* **Tautologia:** Fbf vera in ogni valutazione. 
    $$\vDash P \vee \neg P$$
* **Contraddizione:** Fbf falsa in ogni valutazione. 
    $$\vDash \neg(P \wedge \neg P)$$
* **Contingente:** Fbf vera in alcune valutazioni e falsa in altre (il valore dipende dalle variabili). 
    $$P \rightarrow Q$$
* **Tautologicamente equivalenti:** Quando la formula $\phi \leftrightarrow \psi$ è una tautologia (stessa tavola di verità). 
    $$P \rightarrow Q \equiv \neg P \vee Q$$

---

## Insiemi di Formule

* **Coerente:** Esiste almeno una valutazione che rende VERE tutte le formule dell'insieme contemporaneamente.
    $$\{P, P \rightarrow Q\} \implies P=V, Q=V$$
* **Incoerente:** Non esiste alcuna valutazione che renda vere tutte le formule insieme.
    $$\{P, \neg P\} \implies \text{Impossibile}$$

---

## Proprietà dei Sistemi Logici

### Completezza Funzionale
* **Funzionalmente completo:** Insieme di connettivi in grado di esprimere qualsiasi funzione di verità. 
    * *Esempi:* $\{\neg, \wedge\}$ oppure il solo $\{\text{NAND}\}$.
* **Funzionalmente ridondante:** Insieme completo che contiene connettivi superflui. 
    * *Esempio:* $\{\neg, \wedge, \vee\}$ (dove il $\vee$ si può ricavare da $\neg$ e $\wedge$).

### Funzione di Verità & Decidibilità
* **Funzione di verità:** Funzione che a $n$ valori di verità associa un valore di verità (es. $2^n$).
* **Decidibile:** Esiste un metodo meccanico (algoritmo) che in tempo finito risponde SÌ/NO.
    * **PL:** Sì (es. tavole di verità).
    * **QL:** No (indecidibile al primo ordine).

---

## Metateoremi Principali

### Correttezza (Soundness)
La sintassi rispetta la semantica. Se una formula è dimostrabile, allora è vera in tutti i modelli.
$$\text{Se } \Gamma \vdash \phi \text{ allora } \Gamma \vDash \phi$$
> *Direzione:* Dalla dimostrazione (sintassi) alla verità nei modelli (semantica).

### Completezza (Completeness)
La semantica è coperta dalla sintassi. Se una formula è vera in tutti i modelli, allora è dimostrabile.
$$\text{Se } \Gamma \vDash \phi \text{ allora } \Gamma \vdash \phi$$
> *Direzione:* Dalla verità nei modelli (semantica) alla dimostrazione (sintassi).

---

## Teoremi e Logica dei Predicati (QL)

* **Teorema:** Formula dimostrabile a partire dall'insieme vuoto di premesse.
    $$\vdash P \rightarrow P \quad \text{oppure} \quad \vdash P \vee \neg P$$
* **Verità logica:** Formula vera in ogni modello.
    $$\forall x (x = x) \implies \text{"Tutto è identico a se stesso"}$$
* **Logicamente equivalenti (QL):** Quando $\phi \leftrightarrow \psi$ è una verità logica.
    $$\neg \forall x Fx \equiv \exists x \neg Fx$$

---

## Filosofia del Linguaggio & Semantica

### Uso vs Menzione
* **Uso:** Si usa l'espressione per parlare del mondo. (es. *Il gatto è sul letto*).
* **Menzione:** Si parla dell'espressione stessa. Richiede l'uso delle virgolette. (es. *"Gatto"* ha cinque lettere).

### Riferimento e Sostituzione
* **Coreferenziali:** Termini diversi che si riferiscono allo stesso identico oggetto del mondo. 
    * *Esempio:* "Espero" e "Fosforo" (entrambi si riferiscono al pianeta Venere).
* **Salva Veritate:** Principio per cui due termini coreferenziali sono sostituibili in una frase senza cambiarne il valore di verità.
    * *Contesto estensionale:* "8 è pari" (Vero). Sostituendo con "Il numero dei pianeti" $\rightarrow$ Diventa opaco/falso in base al contesto conoscitivo.

### Quantifier Shift (Fallacia)
Inversione ingiustificata dell'ordine dei quantificatori.
* *Premessa:* "Ogni evento ha una causa". ($\forall x \exists y$)
* *Conclusione fallace:* "Esiste una singola causa per tutti gli eventi". ($\exists y \forall x$)

---

## 4. Alberi Semantici (Regole di Espansione)

Gli alberi semantici verificano la consistenza di un insieme di formule cercando un controesempio. Se tutti i rami si chiudono incontrando una contraddizione esplicita ($P$ e $\neg P$), la formula analizzata (o la negazione della conclusione) è inconsistente.

> ⚠️ **Ordine strategico di espansione (Priorità per evitare rami complessi):**
> 1. Regole che non ramificano (sviluppo in colonna).
> 2. Regole Esistenziali ($\exists$) $\rightarrow$ *Richiedono l'introduzione di una costante individuali completamente nuova.*
> 3. Regole che ramificano (apertura di percorsi alternativi).
> 4. Regole Universali ($\forall$) $\rightarrow$ *Si applicano e riapplicano su tutte le costanti note nel ramo.*

### Meccanismi di Sviluppo dei Nodi:
# Struttura dei Tableaux Logici

Le regole di sviluppo si dividono in **lineari** (sviluppo verticale nello stesso percorso) e **ramificanti** (sdoppiamento del percorso in scenari alternativi).

# Alberi Semantici

## Regole NON Ramificanti (ramo unico)

| Formula | Risultato |
|--------|-----------|
| $\neg\neg P$ | $P$ |
| $P \land Q$ | $P, Q$ |
| $\neg(P \lor Q)$ | $\neg P, \neg Q$ |
| $\neg(P \to Q)$ | $P, \neg Q$ |

## Regole Ramificanti (due rami)

| Formula | Ramo sinistro | Ramo destro |
|--------|---------------|-------------|
| $P \lor Q$ | $P$ | $Q$ |
| $P \to Q$ | $\neg P$ | $Q$ |
| $\neg(P \land Q)$ | $\neg P$ | $\neg Q$ |
| $P \leftrightarrow Q$ | $P, Q$ | $\neg P, \neg Q$ |
| $\neg(P \leftrightarrow Q)$ | $P, \neg Q$ | $\neg P, Q$ |

## Quantificatori

| Formula | Risultato | Note |
|--------|-----------|------|
| $\exists x\, P(x)$ | $P(c)$ | $c$ costante nuova |
| $\neg\forall x\, P(x)$ | $\exists x\, \neg P(x)$ | si riduce a esistenziale |
| $\neg\exists x\, P(x)$ | $\forall x\, \neg P(x)$ | si riduce a universale |
| $\forall x\, P(x)$ | $P(*)$ | ogni termine già presente, riapplicabile |

## Priorità di Applicazione

| Priorità | Regole | Motivo |
|----------|--------|--------|
| 1 — **prima** | Regole non ramificanti | Non aumentano i rami, semplificano subito |
| 2 — **poi** | Esistenziali $\exists$ e $\neg\forall$ | Introducono una costante nuova, non ramificano |
| 3 — **dopo** | Regole ramificanti | Moltiplicano i rami, meglio rimandare |
| 4 — **ultima** | Universali $\forall$ e $\neg\exists$ | Riapplicabili con ogni nuovo termine, usare per ultimi |

> **Nota:** $\neg x = y \equiv \neg(x = y)$

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
