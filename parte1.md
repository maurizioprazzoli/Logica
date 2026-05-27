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
* **Contradd
