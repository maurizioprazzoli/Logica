# Formulario e Regole per l'Esame di Logica

Questo archivio raccoglie in modo ordinato e strutturato le formule utili, le regole di inferenza, le equivalenze logiche e gli schemi di traduzione estratti dal materiale d'esame.

---

## 1. Formule Utili e Regole di Calcolo

### Alberi Semantici (Regole di Espansione)

* **Doppia Negazione ($\neg\neg$):**
  $$\frac{\neg\neg P}{P} \quad \text{(Non ramifica)}$$
* **Disgiunzione ($\vee$):**
  $$\frac{P \vee Q}{P \quad | \quad Q} \quad \text{(Ramifica)}$$
* **Congiunzione ($\wedge$):**
  $$\begin{gathered} P \wedge Q \\ \hline P \\ Q \end{gathered} \quad \text{(In colonna, non ramifica)}$$
* **Condizionale ($\rightarrow$):**
  $$\frac{P \rightarrow Q}{\neg P \quad | \quad Q} \quad \text{(Ramifica)}$$
* **Disgiunzione Negata ($\neg\vee$):**
  $$\begin{gathered} \neg(P \vee Q) \\ \hline \neg P \\ \neg Q \end{gathered} \quad \text{(In colonna, non ramifica)}$$
* **Congiunzione Negata ($\neg\wedge$):**
  $$\frac{\neg(P \wedge Q)}{\neg P \quad | \quad \neg Q} \quad \text{(Ramifica)}$$
* **Condizionale Negato ($\neg\rightarrow$):**
  $$\begin{gathered} \neg(P \rightarrow Q) \\ \hline P \\ \neg Q \end{gathered} \quad \text{(In colonna, non ramifica)}$$
* **Bicondizionale ($\leftrightarrow$):**
  $$\frac{P \leftrightarrow Q}{P \quad | \quad \neg P} \\ \text{     } Q \quad | \quad \neg Q \quad \text{(Ramifica in due coppie)}$$
* **Bicondizionale Negato ($\neg\leftrightarrow$):**
  $$\frac{\neg(P \leftrightarrow Q)}{P \quad | \quad \neg P} \\ \text{     } \neg Q \quad | \quad Q \quad \text{(Ramifica in due coppie)}$$
* **Quantificatore Universale ($\forall$):**
  $$\begin{gathered} \forall x P(x) \\ \hline P(*) \end{gathered} \quad \text{(* dove * è una costante qualsiasi già presente o nuova)}$$
* **Quantificatore Esistenziale ($\exists$):**
  $$\begin{gathered} \exists x P(x) \\ \hline P(c) \end{gathered} \quad \text{(dove c deve essere una costante assolutamente NUOVA)}$$
* **Spostamento Quantificatori Negati:**
  * $\neg\forall x P(x) \equiv \exists x \neg P(x)$
  * $\neg\exists x P(x) \equiv \forall x \neg P(x)$
* **Identità Negata:** $\neg x=y \equiv \neg(x=y)$

> ⚠️ **Ordine strategico di espansione consigliato negli Alberi:**
> 1. Regole senza rami (colonne) $\rightarrow$ 2. Esistenziali ($\exists$) $\rightarrow$ 3. Regole che ramificano $\rightarrow$ 4. Universali ($\forall$)

---

### Regole di Deduzione Naturale

| Regola | Premesse | Conclusione / Azione |
| :--- | :--- | :--- |
| **$\wedge$E** (Eliminazione Congiunzione) | $P \wedge Q$ | $P$ oppure $Q$ |
| **$\vee$I** (Introduzione Disgiunzione) | $P$ | $P \vee Q$ (oppure $Q \vee P$) |
| **$\rightarrow$E** (Modus Ponens) | $P \rightarrow Q, \ P$ | $Q$ |
| **$\leftrightarrow$E** (Eliminazione Bicondizionale) | $P \leftrightarrow Q, \ P$ | $Q$ |
| **$\neg$E** (Eliminazione Negazione) | $\neg\neg P$ | $P$ |

#### Strategie di Deduzione con Ipotesi
* **$\rightarrow$I (Introduzione del Condizionale):** Se la conclusione attesa è $P \rightarrow Q$, apri immediatamente un'ipotesi assumendo l'antecedente $P$ e l'obiettivo diventa derivare il conseguente $Q$.
* **$\neg$I / RAA (Reductio ad Absurdum):** Se la conclusione è atomica o complessa e sei bloccato, ipotizza il contrario di ciò che vuoi dimostrare (es. ipotizza $\neg P$ per dimostrare $P$). Cerca di derivare una contraddizione ($R \wedge \neg R$) per scaricare l'ipotesi.
* **$\vee$E (Eliminazione Disgiunzione):** Se possiedi una premessa disgiuntiva $P \vee Q$, apri due sotto-derivazioni separate: Caso 1 ipotizzando $P$, Caso 2 ipotizzando $Q$. Se giungi alla medesima conclusione $C$ in entrambi i casi, $C$ è dimostrata.
* **$\leftrightarrow$I (Introduzione Bicondizionale):** Apri un'ipotesi $P$ per arrivare a $Q$ (ottenendo $P \rightarrow Q$), poi separatamente apri un'ipotesi $Q$ per arrivare a $P$ (ottenendo $Q \rightarrow P$).

#### Regole per i Quantificatori (Deduzione Naturale)
* **$\forall$E (Eliminazione Universale):** Da $\forall x Fx$ o $\forall x \neg Fx$ ricavi $Fa$ o $\neg Fa$. Puoi istanziarla usando qualsiasi costante già presente o nuova senza vincoli.
* **$\forall$I (Introduzione Universale):** Da $Fa$ passi a $\forall x Fx$. **Vincolo Tassativo:** la costante '$a$' **NON** deve comparire in nessuna ipotesi o assunzione ancora attiva e non scaricata. Devi sostituire tutte le occorrenze di '$a$'.
* **$\exists$I (Introduzione Esistenziale):** Da $Fa$ ricavi $\exists x Fx$. Non ci sono vincoli restrittivi, puoi sostituire anche una sola occorrenza della costante.
* **$\exists$E (Eliminazione Esistenziale):** Se hai una premessa $\exists x Fx$, apri un'ipotesi assumendo $Fa$ dove '$a$' è una **costante NUOVA** (che non compare nella conclusione né in ipotesi attive) al fine di derivare una conclusione indipendente $C$.

> 💡 **Strategie rapide per la Deduzione:**
> * Conclusione è $P \rightarrow Q$ $\rightarrow$ Apri subito l'ipotesi $P$.
> * Conclusione atomica $\rightarrow$ Applica RAA ipotizzando $\neg P$.
> * Tra le premesse c'è $P \vee Q$ $\rightarrow$ Usa immediatamente $\vee$E aprendo i due casi.
> * Sei bloccato $\rightarrow$ Tenta la RAA negando l'intera conclusione.

---

## 2. Schemi di Traduzione ed Esercizi d'Esame

### Formulario di Traduzione dei Quantificatori Classici

| Forma Standard | Formulazione Logica Tipica | Equivalente Alternativo |
| :--- | :--- | :--- |
| **Tutti i P sono Q** (Universale Affermativa) | $\forall x (Px \rightarrow Qx)$ | $\neg\exists x (Px \wedge \neg Qx)$ |
| **Alcuni P sono Q / Qualche P è Q** (Esistenziale Aff.) | $\exists x (Px \wedge Qx)$ | $\neg\forall x (Px \rightarrow \neg Qx)$ |
| **Nessun P è Q** (Universale Negativa) | $\forall x (Px \rightarrow \neg Qx)$ | $\neg\exists x (Px \wedge Qx)$ |
| **Non tutti i P sono Q** (Esistenziale Negativa) | $\exists x (Px \wedge \neg Qx)$ | $\neg\forall x (Px \rightarrow Qx)$ |

* **Parole chiave per Universale ($\forall$):** *tutti, ogni, ognuno, ciascuno, qualunque.*
* **Parole chiave per Esistenziale ($\exists$):** *alcuni, qualche, qualcuno, esiste, almeno uno, c'è, vi è.*

---

### Strutture d'Esame Avanzate (Identità e Limitazioni Numeriche)

* **Identità singola** (*Alice non è Bruno*):
  $$\neg(a=b)$$
* **Esclusività singola** (*Solo a è un P*):
  $$Pa \wedge \forall x (Px \rightarrow x=a) \quad \text{oppure} \quad \forall x (Px \leftrightarrow x=a)$$
* **Esclusività plurale** (*Solo Alice e Bruno sono P*):
  $$(Pa \wedge Pb) \wedge \forall x (Px \rightarrow (x=a \vee x=b)) \quad \text{oppure} \quad \forall x (Px \leftrightarrow (x=a \vee x=b))$$
* **Eccezione** (*Tutti i P tranne a sono Q*):
  $$Pa \wedge \neg Qa \wedge \forall x((Px \wedge x \neq a) \rightarrow Qx)$$
* **Esistenza minimale** (*A è P, ma esistono altri P*):
  $$Pa \wedge \exists x (Px \wedge \neg(x = a))$$
* **Unicità** (*C'è esattamente un P*):
  $$\exists x (Px \wedge \forall y (Py \rightarrow y=x))$$
* **Quantità minima** (*Esistono almeno due P*):
  $$\exists x\exists y (Px \wedge Py \wedge x \neq y)$$
* **Limite massimo 1** (*C'è al massimo un P*):
  $$\forall x\forall y ((Px \wedge Py) \rightarrow x=y)$$
* **Limite massimo 2** (*Ci sono al massimo due P*):
  $$\forall x\forall y\forall z((Px \wedge Py \wedge Pz) \rightarrow (x=y \vee x=z \vee y=z))$$
* **Condizionali particolari** (*P solo se Q / Se P allora Q*):
  $$P \rightarrow Q \quad \text{(Esempio: 'Alice ride solo se Bruno scherza' } \rightarrow R \rightarrow S\text{)}$$
* **Q solo se P:**
  $$Q \rightarrow P$$
* **Secondo Ordine** (*Esiste una proprietà X che tutti i P hanno*):
  $$\exists X\forall x(Px \rightarrow Xx)$$
* **Principio di Identità degli Indiscernibili (Leibniz):**
  $$\forall x\forall y(x=y \leftrightarrow \forall X(Xx \leftrightarrow Xy))$$
