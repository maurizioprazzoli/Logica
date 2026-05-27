\documentclass[11pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{booktabs}
\usepackage{array}
\usepackage{geometry}
\usepackage{tcolorbox}

\geometry{margin=2.5cm}

\title{\textbf{Compendio Integrato di Logica Proposizionale e dei Predicati}}
\author{Formulario Completo d'Esame}
\date{}

\begin{document}

\maketitle

\section{Indicatori Argomentativi e Struttura}
Un argomento si compone di premesse e conclusioni. Gli indicatori testuali si dividono in:
\begin{itemize}
    \item \textbf{Indicatori di Premessa:} Introducono le ragioni a supporto (es. \textit{perché, poiché, infatti, giacché, siccome, in quanto, dato che, visto che, dal momento che}).
    \item \textbf{Indicatori di Conclusione:} Introducono l'enunciato finale derivato dalle premesse (es. \textit{quindi, dunque, perciò, pertanto, così, di conseguenza, ne segue che, se ne deduce che}).
\end{itemize}

\section{Equivalenze Logiche Fondamentali}
In questa sezione vengono presentate le equivalenze principali per la Logica Proposizionale (PL) e la Logica dei Predicati (QL).

\begin{small}
\begin{table}[h!]
\centering
\begin{tabular}{lll}
\toprule
\textbf{Formula Originale} & \textbf{Formula Equivalente} & \textbf{Descrizione Teorica} \\ \midrule
$\neg(P \wedge Q)$ & $\neg P \vee \neg Q$ & Prima Legge di De Morgan: la negazione di una congiunzione \\
 & & è logicamente equivalente alla disgiunzione delle negazioni. \\ \addlinespace
$(P \wedge Q)$ & $(Q \wedge P)$ & Proprietà Commutativa della congiunzione. \\ \addlinespace
$\neg(P \vee Q)$ & $\neg P \wedge \neg Q$ & Seconda Legge di De Morgan: la negazione di una disgiunzione \\
 & & è equivalente alla congiunzione delle singole negazioni. \\ \addlinespace
$(P \rightarrow Q)$ & $\neg P \vee Q$ & Definizione del condizionale materiale in termini di disgiunzione. \\ \addlinespace
$(P \rightarrow Q)$ & $\neg Q \rightarrow \neg P$ & Legge di Contrapposizione. \\ \addlinespace
$\neg(P \rightarrow Q)$ & $P \wedge \neg Q$ & Negazione del condizionale: un'implicazione è falsa solo se \\
 & & l'antecedente è vero e il conseguente è falso. \\ \addlinespace
$P$ & $\neg\neg P$ & Legge della Doppia Negazione. \\ \addlinespace
$P \wedge (Q \vee R)$ & $(P \wedge Q) \vee (P \wedge R)$ & Legge Distributiva della congiunzione rispetto alla disgiunzione. \\ \midrule
$\forall x Fx$ & $\neg\exists x \neg Fx$ & Se una proprietà vale per tutti gli $x$, significa che non esiste \\
 & & alcun $x$ per cui tale proprietà non valga. \\ \addlinespace
$\exists x Fx$ & $\neg\forall x \neg Fx$ & Dire che esiste almeno un $x$ con la proprietà $F$ equivale a \\
 & & negare che per tutti gli $x$ valga la proprietà opposta ($\neg F$). \\ \addlinespace
$\forall x \neg Fx$ & $\neg\exists x Fx$ & Se nessuno possiede la proprietà $F$, allora non esiste alcun \\
 & & individuo per cui valga $F$. \\ \addlinespace
$\exists x \neg Fx$ & $\neg\forall x Fx$ & Se esiste un elemento che non è $F$, allora è falso che tutti \\
 & & gli elementi siano $F$. \\ \bottomrule
\end{tabular}
\end{table}
\end{small}

\newpage

\section{Definizioni Semantiche e Teoria dei Modelli}
\begin{itemize}
    \item \textbf{Tautologia:} Una formula ben formata (fbf) che risulta sempre \textit{Vera} sotto qualsiasi valutazione o assegnazione di valori di verità (es. $P \vee \neg P$).
    \item \textbf{Contraddizione:} Una formula ben formata che risulta sempre \textit{Falsa} in ogni possibile valutazione (es. $P \wedge \neg P$).
    \item \textbf{Contingente:} Una formula il cui valore di verità dipende dalle singole assegnazioni: è vera in alcune valutazioni e falsa in altre (es. $P \rightarrow Q$).
    \item \textbf{Argomento Corretto (Sound):} Un argomento che non solo è logicamente valido, ma le cui premesse sono effettivamente vere nel mondo reale.
    \item \textbf{Decidibile:} Una logica per la quale esiste un algoritmo/metodo meccanico in grado di stabilire in un tempo finito se una formula è valida o meno (La Logica Proposizionale è decidibile, la Logica dei Predicati no).
    \item \textbf{Correttezza (Soundness):} Se $\Gamma \vdash \varphi$ allora $\Gamma \models \varphi$. Se una formula è sintatticamente dimostrabile, allora è anche semanticamente vera in tutti i modelli.
    \item \textbf{Completezza:} Se $\Gamma \models \varphi$ allora $\Gamma \vdash \varphi$. Se una formula è logicamente valida (semantica), allora ammette una dimostrazione formale (sintassi).
\end{itemize}

\section{Alberi Semantici (Regole di Espansione)}
Gli alberi semantici verificano la consistenza di un insieme di formule. Se tutti i rami si chiudono introducendo una contraddizione ($P$ e $\neg P$), la formula di partenza è inconsistente.

\begin{tcolorbox}[colback=yellow!10!white,colframe=yellow!70!black,title=Strategia di Risoluzione Consigliata]
Sviluppare l'albero seguendo tassativamente questo ordine di priorità:
\begin{enumerate}
    \item Regole che non ramificano (regole in colonna)
    \item Regole Esistenziali ($\exists$) - \textit{introducono sempre una costante nuova}
    \item Regole che ramificano
    \item Regole Universali ($\forall$) - \textit{istanziabili infinite volte su costanti esistenti}
\end{enumerate}
\end{tcolorbox}

\subsection{Regole Proposizionali}
\begin{itemize}
    \item \textbf{Doppia Negazione:} Data $\neg\neg P$, si scrive direttamente $P$ nello stesso ramo.
    \item \textbf{Congiunzione ($P \wedge Q$):} Non ramifica. Si inseriscono $P$ e $Q$ in colonna l'uno sotto l'altro.
    \item \textbf{Disgiunzione ($P \vee Q$):} Ramifica. L'albero si divide in due percorsi: un ramo con $P$ e un ramo con $Q$.
    \item \textbf{Condizionale ($P \rightarrow Q$):} Ramifica. Si apre un ramo a sinistra con la negazione dell'antecedente ($\neg P$) e un ramo a destra con il conseguente ($Q$).
    \item \textbf{Condizionale Negato ($\neg(P \rightarrow Q)$):} Non ramifica. Equivale alla verità dell'antecedente e alla falsità del conseguente, quindi si scrive in colonna $P$ e sotto $\neg Q$.
    \item \textbf{Bicondizionale ($P \leftrightarrow Q$):} Ramifica in due coppie. Il ramo sinistro contiene $[P, Q]$ e il ramo destro contiene $[\neg P, \neg Q]$.
\end{itemize}

\subsection{Regole per Quantificatori e Identità}
\begin{itemize}
    \item \textbf{Esistenziale ($\exists x P(x)$):} Si elimina il quantificatore sostituendo la variabile con una costante $c$ che sia \textbf{completamente nuova} nell'albero per quell'analisi: $P(c)$.
    \item \textbf{Universale ($\forall x P(x)$):} Si istanzia la variabile con una costante generica $*$ o una già presente nel ramo. Può essere riapplicata se compaiono nuove costanti.
    \item \textbf{Identità Negata:} $\neg x = y$ si tratta come la fbf complessa $\neg(x=y)$, pronta a generare una chiusura qualora nello stesso ramo compaia l'affermazione di uguaglianza $x=y$.
\end{itemize}

\newpage

\section{Deduzione Naturale}

\subsection{Regole di Eliminazione e Introduzione}
\begin{itemize}
    \item $\mathbf{\wedge E}$: Da $P \wedge Q$ si può derivare singolarmente $P$ oppure $Q$.
    \item $\mathbf{\vee I}$: Da una formula $P$ si può derivare qualsiasi disgiunzione contenente $P$ (es. $P \vee Q$).
    \item $\mathbf{\rightarrow E}$ (Modus Ponens): Date le premesse $P \rightarrow Q$ e $P$, si estrae la conclusione $Q$.
    \item $\mathbf{\neg E}$: Da una doppia negazione $\neg\neg P$ si ricava l'affermazione $P$.
\end{itemize}

\subsection{Regole per Quantificatori (Vincoli Sintattici)}
\begin{itemize}
    \item $\mathbf{\forall E}$ (Eliminazione Universale): Da $\forall x Fx$ si deduce $Fa$. La costante $a$ può essere una costante qualsiasi.
    \item $\mathbf{\forall I}$ (Introduzione Universale): Da $Fa$ si deduce $\forall x Fx$. \textbf{Vincolo fondamentale:} La costante $a$ non deve apparire in nessuna ipotesi o assunzione ancora aperta e attiva all'interno della derivazione.
    \item $\mathbf{\exists I}$ (Introduzione Esistenziale): Da $Fa$ si deduce $\exists x Fx$. Non vi sono vincoli particolari sulla scelta di riscrittura della variabile.
    \item $\mathbf{\exists E}$ (Eliminazione Esistenziale): Se si ha come premessa $\exists x Fx$, si apre un'ipotesi temporanea introducendo un termine $Fa$. \textbf{Vincolo fondamentale:} La costante $a$ dev'essere \textbf{nuova}, ovvero non deve comparire né nella conclusione finale dell'argomento né in altre assunzioni attive.
\end{itemize}

\section{Schemi Pratici di Traduzione d'Esame}

\subsection{Strutture Standard}
\begin{itemize}
    \item \textit{Tutti i P sono Q:} $\forall x (Px \rightarrow Qx)$
    \item \textit{Alcuni P sono Q:} $\exists x (Px \wedge Qx)$
    \item \textit{Nessun P è Q:} $\forall x (Px \rightarrow \neg Qx)$
    \item \textit{Non tutti i P sono Q:} $\exists x (Px \wedge \neg Qx)$
\end{itemize}

\subsection{Strutture Avanzate con Identità e Quantità}
\begin{itemize}
    \item \textit{Solo $a$ è un P (Esclusività singola):}
    $$\forall x (Px \leftrightarrow x=a)$$
    \item \textit{Solo Alice ($a$) e Bruno ($b$) sono P (Esclusività plurale):}
    $$\forall x (Px \leftrightarrow (x=a \vee x=b))$$
    \item \textit{Tutti i P tranne $a$ sono Q (Eccezione):}
    $$Pa \wedge \neg Qa \wedge \forall x ((Px \wedge x \neq a) \rightarrow Qx)$$
    \item \textit{C'è esattamente un P (Unicità assoluta):}
    $$\exists x (Px \wedge \forall y (Py \rightarrow y=x))$$
    \item \textit{Esistono almeno due P:}
    $$\exists x \exists y (Px \wedge Py \wedge x \neq y)$$
    \item \textit{C'è al massimo un P:}
    $$\forall x \forall y ((Px \wedge Py) \rightarrow x=y)$$
    \item \textit{Ci sono al massimo due P:}
    $$\forall x \forall y \forall z ((Px \wedge Py \wedge Pz) \rightarrow (x=y \vee x=z \vee y=z))$$
    \item \textit{Alice ride ($R$) solo se Bruno scherza ($S$):}
    $$R \rightarrow S$$
\end{itemize}

\subsection{Logica del Secondo Ordine}
\begin{itemize}
    \item \textit{Esiste una proprietà $X$ che tutti i $P$ hanno:}
    $$\exists X \forall x (Px \rightarrow Xx)$$
    \item \textit{Principio di Identità degli Indiscernibili (Leibniz):}
    $$\forall x \forall y (x=y \leftrightarrow \forall X (Xx \leftrightarrow Xy))$$
\end{itemize}

\end{document}
