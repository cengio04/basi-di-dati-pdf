![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.001.png) ![ref1]

LinguaggioSQL![ref2]

Linguaggio SQL: fondamenti![ref3]

➢Linguaggio SQL

➢Istruzione del linguaggio ➢Notazione e base di dati di esempio ➢Istruzione SELECT

➢Funzioni aggregate

➢Operatore GROUP BY

1![ref4]

|Il linguaggio SQL||||
| - | :- | :- | :- |
|<p>- Linguaggio per gestire le basi di dati relazionali</p><p>&emsp;- Structured Query Language</p><p>- SQL include istruzioni per</p><p>&emsp;- definire lo schema di una base di dati relazionale</p><p>&emsp;- leggere e scrivere i dati</p><p>&emsp;- definire lo schema di tabelle derivate</p><p>&emsp;- definire i privilegi di accesso degli utenti</p><p>&emsp;- gestire le transazioni</p><p>- Il linguaggio è utilizzabile in modalità</p><p>&emsp;- interattiva</p><p>&emsp;- compilata</p><p>&emsp;&emsp;- un linguaggio ospite (host) contiene le istruzioni SQL</p><p>&emsp;&emsp;- le istruzioni SQL si distinguono dalle istruzioni del linguaggio mezzo di opportuni artifici sintattici</p><p>![ref4]</p>|ospite|per |2|

Il linguaggio SQL![ref3]

- Il linguaggio SQL è un linguaggio a livello di set
  - gli operatori operano su relazioni
  - il risultato è sempre una relazione
- Il linguaggio SQL è *dichiarativo*
  - descrive *cosa fare* e non come fare
  - si pone ad un livello di astrazione superiore rispetto ai linguaggi di programmazione tradizionali

3![ref4]

Istruzionidel linguaggioSQL

Linguaggio SQL![ref2]

4![ref4]

Il linguaggioSQL![ref3]

- Può essere diviso in 
  - DML (Data Manipulation Language)
    - linguaggio di manipolazione dei dati
  - DDL (Data Definition Language) 
    - linguaggio di definizione della struttura della base di dati

5![ref4]

Data Manipulation Language![ref3]

- Interrogazione di una base dati per estrarre i dati di interesse
  - SELECT
- Modifica dell’istanza di una base dati
  - INSERT: inserimento di nuove informazioni in una tabella
  - UPDATE: aggiornamento di dati presenti nella base dati
  - DELETE: cancellazione di dati obsoleti

6![ref4]

|Data Definition Language||
| - | :- |
|<p>- Definizione dello schema di una base di dati</p><p>- creazione, modifica e cancellazione di tabelle: CREATE, ALTER, DROP TABLE</p><p>- Definizione di tabelle derivate</p><p>- creazione, modifica e cancellazione di tabelle il cui contenuto è ottenuto da altre tabelle della base dati: CREATE, ALTER, DROP VIEW</p><p>- Definizione di strutture dati accessorie per recuperare efficientemente i dati</p><p>- creazione e cancellazione di indici: CREATE, DROP INDEX</p><p>- Definizione dei privilegi di accesso degli utenti</p><p>- concessione e revoca di privilegi sulle risorse: GRANT, REVOKE</p><p>- Definizione di transazioni</p><p>- terminazione di una transazione: COMMIT, ROLLBACK</p><p>![ref4]</p>|7|

Notazionee base di dati di 

esempio

Linguaggio SQL![ref2]

8![ref4]

|Sintassi||
| - | :- |
|<p>- Notazione</p><p>&emsp;- parole chiave del linguaggio</p><p>&emsp;&emsp;- caratteri maiuscoli e colore rosso scuro </p><p>- termini variabili</p><p>- corsivo</p><p>- Grammatica</p><p>&emsp;- parentesi angolari < ></p><p>- isolano un termine della sintassi</p><p>- parentesi quadre [ ]</p><p>- indicano che il termine all’interno è opzionale</p><p>- parentesi graffe { } </p><p>- indicano che il termine racchiuso può non comparire o essere ripetuto un numero arbitrario di volte</p><p>- barra verticale |</p><p>- indica che deve essere scelto uno tra i termini separati dalle barre</p><p>![ref4]</p>|9|
|Base dati di esempio: Forniture-Prodotti||
|||
|<p>Chiave  Chiave ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.006.png)esterna  esterna </p><p>P</p><p>CodP</p>||
||||Maglia|Rosso|40|Torino|||||<p>Qta</p><p>300</p><p>200</p><p>400</p>|
||P1||||||||||
||P2|Jeans|Verde|48|Milano|||||
||P2|Jeans|Verde|48|Milano||||
|||||||CodF||CodP||
||P3|Camicia|Blu|48|Roma|||||
|||||||F1|P1||
||P4|Camicia|Blu|44|Torino||||
|||||||F1|P2||
||P5|Gonna|Blu|40|Milano||||
|||||||F1|P3||
|||F1|P4|200||
|||||||
|F1|P5|100||
||||||
|CodF|||||
||F2|P1|300||
|F1|||||
||F2|P2|400||
|F2|||||
||F3|P2|200||
|F3|||||
||F4|P3|200||
|F4||
||F5|Matteo|3|Venezia|||
|![ref4]|10|
|Base dati di esempio: Forniture-Prodotti||
|<p>- Base dati forniture prodotti</p><p>- tabella P: descrive i prodotti disponibili </p><p>- chiave primaria: CodP</p><p>- tabella F: descrive i fornitori </p><p>- chiave primaria: CodF</p><p>- tabella FP: descrive le forniture, mettendo in relazione i prodotti con i fornitori che li forniscono </p><p>- chiave primaria: (CodF, CodP)</p><p>- CodF: chiave esterna. CodF (FP) REFERENCES CodF(F)</p><p>- CodP: Chiave esterna. CodP (FP) REFERENCES CodP(P)</p><p>![ref4]</p>|11|

IstruzioneSELECT

Linguaggio SQL![ref2]

12![ref4]

SELECT![ref3]

SELECT [DISTINCT] *ElencoAttributiDaVisualizzare* FROM *ElencoTabelleDaUtilizzare*

[WHERE *CondizioniDiTupla* ]

[GROUP BY *ElencoAttributiDiRaggruppamento* ] [HAVING *CondizioniSuAggregati* ]

[ORDER BY *ElencoAttributiDiOrdinamento* ]

13![ref4]

Istruzione SELECT (n.1)![ref3]

- Trovare il codice e il numero di soci dei fornitori  di Milano

R

SELECT CodF, NSoci ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.007.png)

FROM    F pCodF, NSoci ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.008.png)WHERE Sede='Milano'; sSede='Milano'![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.009.png)

F F

Istruzione SELECT (n.1)![ref3]

CodF NomeF NSoci Sede![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.010.png)

F1 Andrea 2 Torino F2 Luca 1 Milano F3 Antonio 3 Milano F4 Gabriele 2 Torino F5 Matteo 3 Venezia

R

CodF NSoci![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.011.png)![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.012.png)

F2 1 F3 3

Istruzione SELECT (n.1)![ref3]

14![ref4]

Istruzione SELECT (n.2)![ref3]

- Trovare il codice di tutti i prodotti

R ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.013.png)SELECT CodP p

FROM P; CodP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.014.png)

P

P R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.015.png)

CodP NomeP Colore Taglia Magazzino CodP ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.016.png)P1 Maglia Rosso 40 Torino P1 P2 Jeans Verde 48 Milano P2 P3![ref5] Camicia Blu 48 Roma P3 P4 Camicia Blu 44 Torino P4 P5 Gonna Blu 40 Milano P5 P6 Bermuda Rosso 42 Torino P6

![ref4]

Istruzione SELECT (n.3)![ref3]

- Trovare il codice di tutti i prodotti

Istruzione SELECT (n.3)![ref3]

FP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.018.png)

CodF CodP Qta F1 P1 300 F1 P2 200 F1 P3 400 F1 P4 200 F1 P5 100 F1 P6 100 F2 P1 300 F2 P2 400 F3 P2 200 F4 P3 200 F4 P4 300 F4 P5 400

R

CodP ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.019.png)P1 P2 P3![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.020.png)

SELECT CodP P4 FROM FP; P5

P6 P1 P2 P2 P3 P4 P5

Istruzione SELECT (n.3)![ref3]

![ref4]

- Trovare il codice dei prodotti forniti da almeno un fornitore

R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.021.png)

SELECT CodP pCodP ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.022.png)FROM FP;

FP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.023.png)

- Non effettua la rimozione dei duplicati

![ref4]


Eliminazione dei duplicati: DISTINCT![ref3]

- Parola chiave DISTINCT permette l’eliminazione dei duplicati
- Trovare il codice dei prodotti *diversi* forniti da almeno un fornitore FP

  CodF CodP Qta![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.024.png)

  F1 P1 300

  F1 P2 200 R

  F1 P3 400 ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.025.png)

SELECT DISTINCT CodP F1 P4 200 CodP

FROM FP; F1 P5 100 P1

F1 P6 100 P2![ref6]

F2 P1 300 P3

F2 P2 400 P4

F3 P2 200 P5

F4 P3 200 P6

F4 P4 300

F4 P5 400 18![ref4]

Selezione di tutte le informazioni ![ref3]

- Trovare *tutte* le informazioni sui prodotti

SELECT CodP, NomeP, Colore, Taglia, Magazzino FROM P;

oppure

SELECT **\*** FROM P;

R

CodP NomeP Colore Taglia Magazzino![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.027.png)

P1 Maglia Rosso 40 Torino P2 Jeans Verde 48 Milano P3 Camicia Blu 48 Roma P4 Camicia Blu 44 Torino P5 Gonna Blu 40 Milano P6 Bermuda Rosso 42 Torino

Selezionecon espressione![ref3]

- Trovare il codice dei prodotti e la taglia espressa con la misura americana

SELECT CodP, Taglia-14 [AS TagliaUSA] FROM P;

P R

19![ref4]

CodP NomeP Colore Taglia Magazzino![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.028.png)

P1 Maglia Rosso 40 Torino P2 Jeans Verde 48 Milano P3 Camicia Blu 48 Roma P4 Camicia Blu 44 Torino P5 Gonna Blu 40 Milano P6 Bermuda Rosso 42 Torino

CodP TagliaUSA

P1 26![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.029.png)

P2 34![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.030.png)

P3 34

P4 30

P5 26

P6 38

![ref4]

- Definizione di una nuova colonna *temporanea* per l’espressione calcolata
  - il nome della colonna temporanea può essere definito con la parola chiave AS![ref4]

21![ref4]

- Permette di esprimere condizioni di selezione ![ref7]espresse singolarmente ad ogni tupla
- Espressione booleana di predicati

ClausolaWHERE • Predicati semplici

- espressioni di confronto tra attributi e costanti
- ricerca testuale
- valori NULL

21


ClausolaWHERE (n.1)![ref3]

- Trovare il codice dei fornitori di Milano

SELECT CodF

FROM F

WHERE Sede='Milano';

F![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.032.png)

CodF NomeF NSoci Sede R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.033.png)

F1 Andrea 2 Torino CodF ![ref8]F2 Luca 1 Milano F2 F3 Antonio 3 Milano F3 F4 Gabriele 2 Torino

F5 Matteo 3 Venezia

![ref4]

ClausolaWHERE (n.2)![ref3]

- Trovare il codice e il numero di soci dei fornitori che non hanno sede a Milano

SELECT CodF, NSoci FROM F

WHERE Sede<>'Milano';

ClausolaWHERE (n.2)![ref3]

F![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.035.png)

CodF NomeF NSoci Sede

F1 Andrea 2 Torino F2 Luca 1 Milano F3 Antonio 3 Milano F4 Gabriele 2 Torino F5 Matteo 3 Venezia

R

CodF NSoci ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.036.png)![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.037.png)F1 2

F4 2 F5 3

ClausolaWHERE (n.2)![ref3]

![ref4]

Espressioni booleane (n.1)![ref3]

- Trovare il codice dei fornitori di Milano con più di 2 soci

SELECT CodF

FROM F

WHERE Sede='Milano' AND NSoci>2;

F![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.038.png)

CodF NomeF NSoci Sede R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.039.png)

F1 Andrea 2 Torino ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.040.png)

F2 Luca 1 Milano CodF F3 Antonio 3 Milano F3

F4 Gabriele 2 Torino

F5 Matteo 3 Venezia

![ref4]
Espressioni booleane (n.2)![ref3]

- Trovare il codice e il numero di soci dei fornitori di Milano e di Torino 

SELECT CodF, NSoci

FROM F

WHERE Sede='Milano' OR Sede='Torino';

F R

29![ref4]
Espressioni booleane (n.2)![ref3]

CodF NomeF NSoci Sede![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.041.png)

F1 Andrea 2 Torino F2 Luca 1 Milano F3 Antonio 3 Milano F4 Gabriele 2 Torino F5 Matteo 3 Venezia

CodF NSoci F1 2

F2 1 ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.042.png)![ref6]F3 3 F4 2

![ref4]
Espressioni booleane (n.3)![ref3]

- Trovare il codice e il numero di soci dei fornitori che hanno sede a Milano e a Torino
  - la richiesta non può essere soddisfatta
    - ogni fornitore ha una sola sede

F

CodF NomeF NSoci Sede![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.043.png)

F1 Andrea 2 Torino F2 Luca 1 Milano F3 Antonio 3 Milano F4 Gabriele 2 Torino F5 Matteo 3 Venezia

![ref4]



- Operatore LIKE![ref7]

*NomeAttributo* LIKE *StringaDiCaratteri*

Ricerca testuale • il carattere \_ rappresenta un singolo carattere qualsiasi 

(obbligatoriamente presente)

- il carattere % rappresenta una sequenza qualsiasi di n caratteri (anche vuota)

27

Ricerca testuale (n.1)![ref3]

- Trovare il codice e il nome dei prodotti il cui nome inizia con la lettera C

SELECT CodP, NomeP FROM P

WHERE NomeP LIKE 'C%';

P

CodP NomeP Colore Taglia Magazzino![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.044.png)

P1 Maglia Rosso 40 Torino R

P2 Jeans Verde 48 Milano CodP NomeP ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.045.png)![ref8]P3 **C**amicia Blu 48 Roma P3 Camicia P4 **C**amicia Blu 44 Torino P4 Camicia P5 Gonna Blu 40 Milano

P6 Bermuda Rosso 42 Torino

![ref4]
Ricerca testuale (n.2)![ref3]

- L’attributo Indirizzo contiene la stringa ‘Torino’ Indirizzo LIKE '%Torino%'
- Il codice fornitore è pari a 2 e 
  - è preceduto da un carattere ignoto
  - è costituito esattamente da 2 caratteri

CodF LIKE '\_2'

- L’attributo magazzino non contiene una ‘e’ in seconda posizione

Magazzino NOT LIKE  '\_e%'

35![ref4]

- Operatore speciale IS![ref7]

Ricerca di valori  *NomeAttributo* IS [NOT] NULL

NULL

- In presenza di valori NULL qualsiasi predicato di confronto è falso

30


Gestionedi valoriNULL![ref3]

- Trovare il codice e il nome dei prodotti con taglia maggiore di 44

SELECT CodP, NomeP FROM P

WHERE Taglia>44;

P



CodP NomeP Colore Taglia Magazzino![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.046.png)

P1 Maglia Rosso 40 Torino P2 Jeans Verde 48 Milano P3 Camicia Blu 48 Roma P4 Camicia Blu 44 Torino P5 Gonna Blu NULL Milano P6 Bermuda Rosso 42 Torino

R

CodP NomeP ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.047.png)P2 Jeans![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.048.png)

P3 Camicia



- Le tuple per cui la taglia è NULL non sono selezionate: il predicato Taglia>44 è falso
- In presenza di valori NULL qualsiasi predicato di confronto è falso![ref4]

39
Ricercadi valoriNULL (n.1)![ref3]

- Trovare il codice e il nome dei prodotti per cui la taglia non è indicata

SELECT CodP, NomeP FROM P

WHERE Taglia IS NULL;

P

CodP NomeP Colore Taglia Magazzino![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.049.png)

P1 Maglia Rosso 40 Torino R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.050.png)![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.051.png)

P2 Jeans Verde 48 Milano CodP NomeP P3 Camicia Blu 48 Roma P5 Gonna P4 Camicia Blu 44 Torino

P5 Gonna Blu NULL Milano

P6 Bermuda Rosso 42 Torino

![ref4]
Ricerca di valori NULL (n.2)![ref3]

- Trovare il codice e il nome dei prodotti con la taglia maggiore di 44 o che potrebbero avere taglia maggiore di 44

SELECT CodP, NomeP

FROM P

WHERE Taglia>44 OR Taglia IS NULL;

P


Ricerca di valori NULL (n.2)![ref3]

CodP NomeP Colore Taglia Magazzino![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.052.png)

P1 Maglia Rosso 40 Torino P2 Jeans Verde 48 Milano P3 Camicia Blu 48 Roma P4 Camicia Blu 44 Torino P5 Gonna Blu NULL Milano P6 Bermuda Rosso 42 Torino

![ref4]

R

CodP NomeP ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.053.png)P2 Jeans![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.054.png)

P3 Camicia P5 Gonna



- Clausola ORDER BY![ref7]

ORDER BY *NomeAttributo* [ASC | DESC] {, *NomeAttributo* [ASC | DESC] }

Ordinamento 

risultato • Ld’orecrdesinamecente nt(oDEpSC)uò essere crescente (ASC) o 

- L’ordinamento implicito è crescente (ASC)
- Gli attributi di ordinamento devono comparire nella clausola SELECT
  - anche implicitamente (come SELECT \*)

34

Ordinamento del risultato (n.1)![ref3]

- Trovare il codice dei prodotti e la loro taglia ordinando il risultato in ordine decrescente di taglia

SELECT CodP, Taglia FROM P

ORDER BY Taglia DESC;

Ordinamento del risultato (n.1)![ref3]

P![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.055.png)

CodP NomeP Colore Taglia Magazzino

P1 Maglia Rosso 40 Torino P2 Jeans Verde 48 Milano P3 Camicia Blu 48 Roma P4 Camicia Blu 44 Torino P5 Gonna Blu 40 Milano P6 Bermuda Rosso 42 Torino

![ref4]

R

CodP Taglia ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.056.png)P2 48 P3 48 ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.057.png)P4 44 P6 42 P1 40 P5 40

Ordinamento del risultato (n.2)![ref3]

- Trovare tutte le informazioni sui prodotti ordinando il risultato in ordine crescente di nome e decrescente di taglia

SELECT CodP, NomeP, Colore, Taglia, Magazzino SELECT \*

FROM P FROM P

ORDER BY NomeP, Taglia DESC; ORDER BY NomeP, Taglia DESC;

R

CodP NomeP Colore Taglia Magazzino![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.058.png)

P6 Bermuda Rosso 42 Torino

P3 Camicia Blu 48 Roma

P4 Camicia Blu 44 Torino

P5 Gonna Blu 40 Milano

P2 Jeans Verde 48 Milano

P1 Maglia Rosso 40 Torino![ref4]

36

Ordinamento del risultato (n.3)![ref3]

- Trovare il codice dei prodotti e la taglia espressa come taglia americana, ordinando il risultato in ordine crescente di taglia

SELECT CodP, Taglia-14 AS TagliaUSA FROM P

ORDER BY TagliaUSA;

P R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.059.png)![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.060.png)

CodP NomeP Colore Taglia Magazzino CodP TagliaUSA

P1 Maglia Rosso 40 Torino P5 26

P2 Jeans Verde 48 Milano P1 28![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.061.png)

P3 Camicia Blu 48 Roma P6 28

P4 Camicia Blu 44 Torino P4 30

P5 Gonna Blu 40 Milano P2 34

P6 Bermuda Rosso 42 Torino P3 34

37![ref4]


- Definito mediante le clausole FROM e WHERE![ref7]
- Il risultato e l’efficienza dell’interrogazione 
  - sono indipendenti dall’ordine delle tabelle nella clausola FROM
  - sono indipendenti dall’ordine dei predicati nella clausola 

Join • WHl’ordiEREne di esecuzione ottimale è selezionato dal  DBMS 

(modulo ottimizzatore)

- Clausola FROM con N tabelle
  - almeno N-1 condizioni di join nella clausola WHERE 

38

Join (n.1)![ref3]

- Trovare il nome dei fornitori che forniscono il prodotto P2

CodF CodP Qta CodF![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.062.png)![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.063.png) NomeF NSoci Sede F1 P1 300 F1 Andrea 2 Torino F1 P2 200 F2 Luca 1 Milano F1 P3 400 F3 Antonio 3 Milano F1 P4 200 F4 Gabriele 2 Torino F1 P5 100 F5 Matteo 3 Venezia F2 P1 300

F2 P2 400

F3 P2 200

F4 P3 200

39![ref4]

Prodottocartesiano![ref3]

- Trovare il nome dei fornitori che forniscono il prodotto P2

SELECT NomeF FROM F, FP ;

![ref4]

F.CodF F.NomeF F.NSoci F.Sede FP.CodF FP.CodP FP.Qta![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.064.png)

F1 Andrea 2 Torino F1 P1 300

F1 Andrea 2 Torino F1 P2 200

F1 Andrea 2 Torino F1 P3 400

F1 Andrea 2 Torino F1 P4 200

F1 Andrea 2 Torino F1 P5 100

F1 Andrea 2 Torino F1 P6 100

F1 Andrea 2 Torino F2 P1 300

- … … … … … …

F2 Luca 1 Milano F1 P1 300

- … … … … … …

F2 Luca 1 Milano F2 P1 300

- … … … … … …![ref4]

41


Join (n.1)![ref3]

=![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.065.png)

F.CodF F.NomeF F.NSoci F.Sede FP.CodF FP.CodP FP.Qta

*F1 Andrea 2 Torino F1 P1 300 F1 Andrea 2 Torino F1 P2 200 F1 Andrea 2 Torino F1 P3 400 F1 Andrea 2 Torino F1 P4 200 F1 Andrea 2 Torino F1 P5 100 F1 Andrea 2 Torino F1 P6 100* F1 Andrea 2 Torino F2 P1 300

- … … … … … …

F2 Luca 1 Milano F1 P1 300

- … … … … … …

*F2 Luca 1 Milano F2 P1 300*

- … … … … … …![ref4]

42

Join (n.1)![ref3]

=![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.066.png)

F.CodF F.NomeF F.NSoci F.Sede FP.CodF FP.CodP FP.Qta

F1 Andrea 2 Torino F1 P1 300 F1 Andrea 2 Torino F1 P2 200 F1 Andrea 2 Torino F1 P3 400 F1 Andrea 2 Torino F1 P4 200 F1 Andrea 2 Torino F1 P5 100 F1 Andrea 2 Torino F1 P6 100 F2 Luca 1 Milano F2 P1 300 F2 Luca 1 Milano F2 P2 400 F3 Antonio 3 Milano F3 P2 200 F4 Gabriele 2 Torino F4 P3 200 F4 Gabriele 2 Torino F4 P4 300

F4 Gabriele 2 Torino F4 P5 400

43![ref4]

Join (n.1)![ref3]

- Trovare il nome dei fornitori che forniscono il prodotto P2

SELECT NomeF Condizione di join ![ref9]FROM F, FP![ref10]

WHERE F.CodF=FP.CodF ;

![ref11] ![ref12]

NomeTabella.NomeAttributo

44![ref4]

Join (n.1)![ref3]

- Trovare il nome dei fornitori che forniscono il prodotto P2

SELECT NomeF Condizione di join ![ref9]FROM F, FP![ref10]

WHERE F.CodF=FP.CodF AND CodP='P2';

![ref11] ![ref12]

NomeTabella.NomeAttributo

45![ref4]

|Join (n.1)||||||||||||||
| - | :- | :- | :- | :- | :- | :- | :- | :- | :- | :- | :- | :- | :- |
|||||||||||||||
|=|FP.CodP='P2'|||||||||||||
||F.CodF|F.NomeF|F.NSoci|F.Sede|FP.CodF|FP.CodP|FP.Qta|||||||
|||||||||||||||
||F1|Andrea|2|Torino|F1|P1|300|||||||
|||F1|Andrea|2|Torino|F1|P2|200||||||
||F1|Andrea|2|Torino|F1|P3|400|||||||
|||||||||||||||
||F1|Andrea|2|Torino|F1|P4|200|||||||
|||||||||||||||
||F1|Andrea|2|Torino|F1|P5|100|||||||
|||||||||||||||
||F1|Andrea|2|Torino|F1|P6|100|||||||
|||||||||||||||
||F2|Luca|1|Milano|F2|P1|300|||||||
|||F2|Luca|1|Milano|F2|P2|400||||||
|||F3|Antonio|3|Milano|F3|P2|200||||||
||F4|Gabriele|2|Torino|F4|P3|200|||||||
|||||||||||||||
||F4|Gabriele|2|Torino|F4|P4|300|||||||
|||||||||||||||
||F4|Gabriele|2|Torino|F4|P5|400|||||||
|![ref4]|46|||||||||||||

Join (n.1)![ref3]

F.CodF F.NomeF F.NSoci F.Sede FP.CodF FP.CodP FP.Qta![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.071.png)

F1 Andrea 2 Torino F1 P2 200 F2 Luca 1 Milano F2 P2 400 F3 Antonio 3 Milano F3 P2 200

![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.072.png)

R

NomeF ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.073.png)Andrea Luca Antonio

47![ref4]

Join (n.1)  ![ref3]

- Trovare il nome dei fornitori che forniscono il prodotto P2
  - in algebra relazionale

pF.NomeF

F sCodP=‘P2’![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.074.png)

FP

pF.NomeF

sCodP=‘P2’![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.075.png)![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.076.png)

F FP

![ref4]

Join (n.1)  ![ref3]

- Trovare il nome dei fornitori che forniscono il prodotto P2
  - in algebra relazionale

SELECT NomeF ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.077.png)FROM F, FP WHERE F.CodF=FP.CodF 

AND CodP='P2';

SELECT NomeF

FROM FP,F

WHERE CodP='P2' AND 

F.CodF=FP.CodF;

- Il risultato e l’efficienza sono indipendenti 
  - dall’ordine dei predicati nella clausola WHERE
  - dall’ordine delle tabelle nella clausola FROM

![ref4]

Dichiarativitàdel linguaggioSQL![ref3]

- In algebra relazionale (linguaggio procedurale) si definisce l’ordine in cui sono applicati gli operatori 
- In SQL (linguaggio dichiarativi) l’ordine migliore è scelto dall’ottimizzatore indipendentemente 
  - dall’ordine delle condizioni nella clausola WHERE
  - dall’ordine delle tabelle nella clausola FROM

![ref4]

Join (n.2)![ref3]

- Trovare il nome dei fornitori che forniscono almeno un prodotto rosso

SELECT NomeF

FROM F, FP, P

WHERE  F.CodF=FP.CodF AND P.CodP=FP.CodP

AND Colore='Rosso';

- Clausola FROM con N tabelle
  - almeno N-1 condizioni di join nella clausola WHERE 

![ref4]

Join (n.2)![ref3]

- Trovare le coppie di codici dei fornitori tali che entrambi i fornitori abbiano sede nella stessa città

SELECT FX.CodF, FY.CodF FROM F AS FX, F AS FY WHERE  FX.Sede=FY.Sede;

F AS FX![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.078.png)

CodF NomeF NSoci Sede

F1 Andrea 2 Torino F2 Luca 1 Milano F3 Antonio 3 Milano F4 Gabriele 2 Torino F5 Matteo 3 Venezia

![ref4]

F AS FY

CodF NomeF NSoci Sede![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.079.png)

F1 Andrea 2 Torino F2 Luca 1 Milano F3 Antonio 3 Milano F4 Gabriele 2 Torino F5 Matteo 3 Venezia

52

Join (n.2)![ref3]

- Trovare le coppie di codici dei fornitori tali che entrambi i fornitori abbiano sede nella stessa città

SELECT FX.CodF, FY.CodF

FROM F AS FX, F AS FY R

WHERE  FX.Sede=FY.Sede; FX.CodF FY.CodF![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.080.png)

F1 F1 F1 F4 F2 F2 F2 F3

- Sono presenti F3 F2
  - coppie di valori uguali F3 F3
  - permutazioni della stessa coppia di valori F4 F1 F4 F4 F5 F5

53![ref4]

Join (n.2)![ref3]

- Trovare le coppie di codici dei fornitori tali che entrambi i fornitori abbiano sede nella stessa città

SELECT FX.CodF, FY.CodF

FROM F AS FX, F AS FY R

WHERE  FX.Sede=FY.Sede AND  ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.081.png)

FX.CodF FY.CodF FX.CodF <> FY.CodF; F1 F1

F1 F4 F2 F2 F2 F3

- Elimina le coppie di valori uguali F3 F2 ~~F3 F3~~ F4 F1 ~~F4 F4~~ F5 F5

54![ref4]

Join (n.2)![ref3]

- Trovare le coppie di codici dei fornitori tali che entrambi i fornitori abbiano sede nella stessa città

SELECT FX.CodF, FY.CodF

FROM F AS FX, F AS FY R

WHERE  FX.Sede=FY.Sede AND  FX.CodF FY.CodF![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.082.png)

FX.CodF < FY.CodF; F1 F1

F1 F4

F2 F2 R

F2 F3 FX.CodF FY.CodF Elimina le permutazioni della stessa coppia  F3 F2 F1 F4

- di valori ~~F3 F3~~ F2 F3 F4 F1

  ~~F4 F4~~

  F5 F5

55![ref4]

|Join: sintassialternativa|||
| - | :- | :- |
|<p>- Permette di specificare diversi tipi di join</p><p>&emsp;- outer join</p><p>- Permette di distinguere </p><p>&emsp;- condizioni di join </p><p>&emsp;- condizioni di selezione sulle tuple</p><p>SELECT [DISTINCT] *Attributi* FROM *Tabella TipoJoin* JOIN *Tabella*</p><p>*CondizioneDiJoin*</p><p>[WHERE *CondizioniDiTupla*];</p><p>*TipoJoin* = < INNER | [FULL | LEFT | RIGHT] OUTER ></p><p>![ref4]</p>|ON|56|

INNER join![ref3]

- Trovare il nome dei fornitori che forniscono almeno un prodotto rosso

SELECT NomeF

FROM P INNER JOIN FP ON P.CodP=FP.CodP

INNER JOIN F ON F.CodF=FP.CodF WHERE P.Colore='Rosso';

57![ref4]

OUTER join![ref3]

- Trovare il codice e il nome dei fornitori insieme al codice dei relativi prodotti forniti, visualizzando anche i fornitori che non hanno forniture

F.CodF F.NomeF FP.CodP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.083.png)

F1 Andrea P1

F1 Andrea P2

F1 Andrea P3

SELECT F.CodF, NomeF, CodP F1 Andrea P4

FROM F LEFT OUTER JOIN FP ON   F1 Andrea P5

F1 Andrea P6 F.CodF=FP.CodF; F2 Luca P1

F2 Luca P2

F3 Antonio P2

F4 Gabriele P3

F4 Gabriele P4

F4 Gabriele P5

*F5 Matteo NULL* 58![ref4]


Funzioniaggregate

Introduzione a SQL![ref2]

59![ref4]

Funzioneaggregata![ref3]

- Opera su un insieme di valori
- Produce come risultato un unico valore (aggregato)
- E’ indicata nella clausola SELECT
  - non si possono indicare anche attributi non aggregati
  - possono essere richieste più funzioni aggregate contemporaneamente
- Le funzioni aggregate sono valutate solo dopo l’applicazione di tutti i predicati nella clausola WHERE 

60![ref4]

Funzioniaggregate![ref3]

COUNT: conteggio degli elementi in un attributo ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.084.png)SUM: somma dei valori di un attributo![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.085.png)

AVG: media dei valori di un attributo ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.086.png)

MAX: massimo valore di un attributo![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.087.png)

MIN: minimo valore di un attributo![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.088.png)

61![ref4]


- Conteggio del numero di elementi di un insieme![ref7]
  - righe di una tabella 
  - valori (eventualmente distinti) di uno o più attributi

COUNT COUNT (<\*| [DISTINCT | ALL] ListaAttributi >)}

- Se l’argomento della funzione è preceduto da DISTINCT, conta il numero di valori distinti dell’argomento

62

FunzioneCOUNT (n.2)![ref3]

- Trovare il numero di fornitori 

SELECT COUNT(**\***) FROM F;

F![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.089.png)

CodF NomeF NSoci Sede R

F1 Andrea 2 Torino ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.090.png)![ref13]

F2 Luca 1 Milano 

F3 Antonio 3 Milano 5 F4 Gabriele 2 Torino

F5 Matteo 3 Venezia

63![ref4]

- Trovare il numero di fornitori che hanno almeno una fornitura 

FP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.092.png)

CodF CodP Qta SELECT COUNT(**\***)

F1 P1 300 FROM FP;

F1 P2 200

F1 P3 400 R

F1 P4 200 ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.093.png)![ref6]

F1 P5 100 

12

F1 P6 100

F2 P1 300

F2 P2 400

F3 P2 200 Conta il numero di forniture, non di fornitori F4 P3 200

F4 P4 300

F4 P5 400

64![ref4]

- Trovare il numero di fornitori che hanno almeno una fornitura 

FP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.094.png)

CodF CodP Qta SELECT COUNT(CodF)

F1 P1 300 FROM FP;

F1 P2 200

F1 P3 400 R

F1 P4 200 ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.095.png)![ref13]

F1 P5 100 

12

F1 P6 100

F2 P1 300

F2 P2 400

F3 P2 200 Conta il numero di forniture, non di fornitori F4 P3 200

F4 P4 300

F4 P5 400

65![ref4]

- Trovare il numero di fornitori che hanno almeno una fornitura 

FP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.096.png)

CodF CodP Qta SELECT COUNT(DISTINCT CodF)

F1 P1 300 FROM FP;

F1 P2 200

F1 P3 400 R

F1 P4 200 ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.097.png)![ref14]

F1 P5 100 

4

F1 P6 100

F2 P1 300

F2 P2 400 Conta il numero di fornitori diversi F3 P2 200

F4 P3 200

F4 P4 300

F4 P5 400

66![ref4]


Funzioni aggregate  • Le funzioni aggregate sono valutate solo dopo ![ref7]l’applicazione di tutti i predicati nella clausola 

e WHERE WHERE

93
||Funzioniaggregate e WHERE|||||
| :- | - | :- | :- | :- | :- |
|•|<p>Trovare il numero di fornitori che forniscono il prodotto P2</p><p>FP</p><p>SELECT COUNT(**\***) </p><p>CodF</p><p>CodP</p><p>Qta</p>|||||
|||F1|P1|300|<p>FROM FP</p><p>WHERE CodP='P2';</p>|
|||F1|P2|200||
|||F1|P3|400||
|||F1|P4|200|<p>R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.099.png)![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.100.png)![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.101.png)</p><p>CodF CodP Qta ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.102.png)F1 P2 200 F2 P2 400 F3 P2 200 </p><p>3</p>|
|||F1|P5|100||
|||F1|P6|100||
|||F2|P1|300||
|||F2|P2|400||
|||F3|P2|200||
|||F4|P3|200||
|||F4|P4|300||
|||F4|P5|400||
|<p>•</p><p>![ref4]</p>|<p>Le funzioni aggregate sono valutate solo dopo l’applicazione di tutti i predicati nella clausola WHERE</p><p>68</p>|||||

- SUM, MAX, MIN e AVG![ref7]
  - ammettono come argomento un attributo o un’espressione


SUM, MAX, 

MIN, AVG

- SUM e AVG 
  - ammettono come argomento solo attributi di tipo numerico o intervallo di tempo 
- MAX e MIN
  - richiedono che l’espressione sia ordinabile
  - possono essere applicate anche su stringhe di caratteri e istanti di tempo 


Esempio: SUM![ref3]

- Trovare la quantità totale di pezzi forniti per il prodotto P2

FP

CodF CodP Qta SELECT SUM(Qta) ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.103.png)

F1 P1 300 FROM FP

FF11 PP23 240000 WHERE CodP='P2';

F1 P4 200

F1 P5 100 CodF CodP Qta R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.104.png)![ref14]![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.105.png)

F1 P6 100 F1 P2 200 ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.106.png)

F2 P1 300 F2 P2 400 800 F2 P2 400

F3 P2 200

F3 P2 200

F4 P3 200

F4 P4 300

F4 P5 400

70![ref4]


OperatoreGROUP BY

Introduzione a SQL![ref2]

71![ref4]

- Clausola di raggruppamento![ref7]

GROUP BY ElencoAttributiDiRaggruppamento

- L’ordine degli attributi di raggruppamento è ininfluente 
- Nella clausola SELECT possono comparire *solo*

GROUP BY • attributi presenti nella clausola GROUP BY 

- funzioni aggregate
- Gli attributi univocamente determinati da attributi già presenti nella clausola GROUP BY possono essere aggiunti senza alterare il risultato

72

Raggruppamento![ref3]

- *Per ogni prodotto*, trovare la quantità totale di pezzi forniti

FP FP

Raggruppamento![ref3]

- *Per ogni prodotto*, trovare la quantità totale di pezzi forniti

CodF CodP Qta ![ref15]F1 P1 300 F1 P2 200 F1 P3 400 F1 P4 200 F1 P5 100 F1 P6 100 F2 P1 300 F2 P2 400 F3 P2 200 F4 P3 200 F4 P4 300 F4 P5 400

CodF CodP Qta

F1 P1 300 R![ref16]![ref17]

F2 P1 300 CodP

F1 P2 200

P1 600 F2 P2 400

F3 P2 200 P2 800 ![ref18]![ref19]F1 P3 400 P3 600 F4 P3 200 P4 500 F1 P4 200 P5 500 F4 P4 300 P6 100 F1 P5 100

F4 P5 400

F1 P6 100

Raggruppamento![ref3]

- *Per ogni prodotto*, trovare la quantità totale di pezzi forniti

73![ref4]

FP FP

Raggruppamento![ref3]

- *Per ogni prodotto*, trovare la quantità totale di pezzi forniti

CodF CodP Qta ![ref15]F1 P1 300 F1 P2 200 F1 P3 400 F1 P4 200 F1 P5 100 F1 P6 100 F2 P1 300 F2 P2 400 F3 P2 200 F4 P3 200 F4 P4 300 F4 P5 400

CodF CodP Qta

F1 P1 300 R![ref16]![ref17]

F2 P1 300 CodP

F1 P2 200

P1 600 SELECT CodP, SUM(Qta) F2 P2 400

F3 P2 200 P2 800 FROM FP![ref18]![ref19]

F1 P3 400 P3 600

F4 P3 200 P4 500 GROUP BY CodP;

F1 P4 200 P5 500

F4 P4 300 P6 100

F1 P5 100

F4 P5 400

F1 P6 100

Raggruppamento![ref3]

- *Per ogni prodotto*, trovare la quantità totale di pezzi forniti

74![ref4]

GROUP BY e WHERE![ref3]

- Per ogni prodotto, trovare la quantità totale di pezzi forniti da 

fornitori con sede a Milano

FP

CodF CodP Qta ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.112.png)F F1 P1 300![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.113.png)

CodF NomeF NSoci Sede F1 P2 200 F1 Andrea 2 Torino F1 P3 400

F2 Luca 1 Milano F1 P4 200 F3 Antonio 3 Milano F1 P5 100 F4 Gabriele 2 Torino F1 P6 100 F5 Matteo 3 Venezia F2 P1 300 F2 P2 400

F3 P2 200

F4 P3 200

F4 P4 300

F4 P5 400

75![ref4]

GROUP BY e WHERE![ref3]

- Per ogni prodotto, trovare la quantità totale di pezzi forniti da fornitori con sede a Milano

SELECT   ...

FROM FP, F

WHERE FP.CodF=F.CodF AND Sede='Milano' ...

76![ref4]

GROUP BY e WHERE![ref3]

- Per ogni prodotto, trovare la quantità totale di pezzi forniti da 

fornitori con sede a Milano

F.CodF F.NomeF F.NSoci F.Sede FP.CodF FP.CodP FP.Qta![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.114.png)

F1 Andrea 2 Torino F1 P1 300 F1 Andrea 2 Torino F1 P2 200 F1 Andrea 2 Torino F1 P3 400 F1 Andrea 2 Torino F1 P4 200 F1 Andrea 2 Torino F1 P5 100 F1 Andrea 2 Torino F1 P6 100 *F2 Luca 1 Milano F2 P1 300 F2 Luca 1 Milano F2 P2 400 F3 Antonio 3 Milano F3 P2 200* F4 Gabriele 2 Torino F4 P3 200 F4 Gabriele 2 Torino F4 P4 300

F4 Gabriele 2 Torino F4 P5 400

77![ref4]

fornitori con sede a Milano

SELECT CodP, SUM(Qta) 

FROM FP, F

WHERE FP.CodF=F.CodF AND Sede='Milano' GROUP BY CodP;

- I prodotti senza forniture non sono inclusi nel risultato

78![ref4]

fornitori con sede a Milano

GROUP BY e WHERE![ref3]

- Per ogni prodotto, trovare la quantità totale di pezzi forniti da 

FP.CodP FP.Qta![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.115.png)

P1 300 P2 400 P2 200

R

FP.CodP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.116.png)![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.117.png)

P1 300 P2 600

GROUP BY e WHERE![ref3]

- Per ogni prodotto, trovare la quantità totale di pezzi forniti da 

79![ref4]


GROUP BY e SELECT![ref3]

- Per ogni prodotto, trovare il codice, *il nome* e la quantità totale fornita

SELECT P.CodP, *NomeP*, SUM(Qta) FROM P, FP

WHERE P.CodP=FP.CodP

GROUP BY P.CodP, *NomeP*

- Gli attributi univocamente determinati da attributi già presenti nella clausola GROUP BY possono essere aggiunti *senza alterare il risultato*

80![ref4]

- Non è possibile utilizzare la clausola WHERE per ![ref7]definire condizioni di selezione sui gruppi

Condizione di • Condizione di selezione sui gruppi espressa in 

selezione sui  clausola HAVING:

gruppi: HAVING HAVING Condizioni di gruppo

- permette di specificare condizioni *solo* su funzioni aggregate

81

Condizione di selezione sui gruppi (n.1)![ref3]

- Trovare la quantità totale di pezzi forniti per i prodotti per cui sono forniti *in totale* almeno 600 pezzi

Condizione di selezione sui gruppi (n.1)![ref3]

FP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.118.png)

CodF CodP Qta

F1 P1 300 F1 P2 200 F1 P3 400 F1 P4 200 F1 P5 100 ![ref5]F1 P6 100 F2 P1 300 F2 P2 400 F3 P2 200 F4 P3 200 F4 P4 300 F4 P5 400

![ref4]

FP

CodF CodP Qta![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.119.png)

F1 P1 300

F2 P1 300

F1 P2 200 R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.120.png)

F2 P2 400 CodP

F3 P2 200 ![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.121.png)

P1 600

F1 P3 400

F4 P3 200 P2 800 F1 P4 200 P3 600 F4 P4 300

F1 P5 100

F4 P5 400

F1 P6 100

82

Condizione di selezione sui gruppi (n.1)![ref3]

- Trovare la quantità totale di pezzi forniti per i prodotti per cui sono forniti *in totale* almeno 600 pezzi

SELECT CodP, SUM(Qta) FROM FP

GROUP BY CodP

HAVING SUM(Qta)>=600;

- La clausola HAVING permette di specificare condizioni su funzioni aggregate

83![ref4]

Condizione di selezione sui gruppi (n.2)![ref3]

- Trovare il codice dei prodotti rossi forniti da più di un fornitore

FP![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.122.png)

P CodF CodP Qta F1 P1 300![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.123.png)

CodP NomeP Colore Taglia Magazzino F1 P2 200 P1 Maglia Rosso 40 Torino F1 P3 400 P2 Jeans Verde 48 Milano F1 P4 200 P3 Camicia Blu 48 Roma F1 P5 100 P4 Camicia Blu 44 Torino F1 P6 100 P5 Gonna Blu 40 Milano F2 P1 300 P6 Bermuda Rosso 42 Torino F2 P2 400

F3 P2 200

F4 P3 200

F4 P4 300

F4 P5 400

84![ref4]

- Trovare il codice dei prodotti rossi forniti da più di un fornitore

SELECT FP.CodP

FROM FP, P

WHERE FP.CodP=P.CodP AND Colore='Rosso' GROUP BY FP.CodP

HAVING COUNT(**\***)>1;

85![ref4]

- Trovare il codice dei prodotti rossi forniti da più di un fornitore

F.CodF F.CodP F.Qta P.CodP P.NomeP P.Colore P.Taglia P.Magazzino![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.124.png)

F1 P1 300 P1 Maglia Rosso 40 Torino F2 P1 300 P1 Maglia Rosso 40 Torino F1 P6 100 P6 Bermuda Rosso 42 Torino

![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.125.png)

R![](Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.126.png)

CodP P1

86![ref4]

[ref1]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.002.png
[ref2]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.003.png
[ref3]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.004.png
[ref4]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.005.png
[ref5]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.017.png
[ref6]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.026.png
[ref7]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.031.png
[ref8]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.034.png
[ref9]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.067.png
[ref10]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.068.png
[ref11]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.069.png
[ref12]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.070.png
[ref13]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.091.png
[ref14]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.098.png
[ref15]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.107.png
[ref16]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.108.png
[ref17]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.109.png
[ref18]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.110.png
[ref19]: Aspose.Words.6da9cfce-ab9d-4be8-9d1a-e7240a017861.111.png
