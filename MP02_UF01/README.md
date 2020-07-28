<h1 style="font-size: 2.5em; padding-bottom: .3em; border-bottom: 2px solid #eaecef;">UF01: Introducció a les bases de dades</h1>

Actualment estem absolutament envoltats d'**informació** la qual, en el **99%** de les vegades esta emmagatzemada en una **base de dades**.

Les dades que s'utilitzen en els sistemes d'informació (<span style="font-size:1.25em; text-decoration:underline;">**SI**</span>) s'acostumen a emmagatzemar en bases de dades (<span style="font-size:1.25em; text-decoration:underline;">**BD**</span>). Per a poder parlar i raonar amb certa propietat sobre les BD, ens convindrà tenir clar què són <span style="font-size:1.25em; text-decoration:underline;">les **dades**</span>, que és <span style="font-size:1.25em; text-decoration:underline;">l'**informació**</span>, i quines són <span style="font-size:1.25em; text-decoration:underline;">les **abstraccions**</span> que els informàtics representem físicament sobre discs magnètics, CD-ROM, cartutxos de cinta, etc. Amb aquest objectiu, haurem d'adquirir algunes nocions teòriques fonamentals i disposar d'eines formals en què basar-nos.

Tot informàtic que hagi de treballar amb **bases de dades** (```BD```), és imprescindible que sàpiga distingir tres àmbits ben diferenciats, però que al mateix temps estan fortament interrelacionats, els quals fan referència, respectivament, a **la realitat**, a la seva **conceptualització**, i a la seva **representació informàtica**.

Anomeneu exemples diaris en que creieu que hi ha informació emmagatzemada en una base de dades.
1. Treure calers d'un caixer automàtic.
1. ...

Per tant, com a tècnics superiors en informàtica, cal que tingueu molt clars tot un seguit de conceptes relacionats amb les **dades** i de la seva **representació informàtica**.

Per començar cal entendre que hi ha tres àmbits que hem de ser capaços de diferenciar per tal de treballar correctament amb les dades: <span style="font-size:1.25em; text-decoration:underline;">el **món real**</span> amb els objectes del nostre interès, <span style="font-size:1.25em; text-decoration:underline;">el **món conceptual**</span> que conté el conjunt dels coneixements obtinguts observant el **món real** i <span style="font-size:1.25em; text-decoration:underline;">el **món de les representacions**</span> que no deixen de ser representacions físiques dels coneixements que tenim dels objectes del **món real**.

## 1. Els tres mons: el **real**, el **conceptual** i el de les **representacions**.

Per **món real**, s'entén la part de la realitat (ja sigui tangible o intangible) que en un moment determinat ens interessa informatitzar perquè hem rebut un encàrrec en aquest sentit. 
Així doncs, mitjançant l'observació de la realitat, s'obté un conjunt d'abstraccions de les informacions considerades rellevants, es construeix un **model que conceptualitza** els aspectes de la realitat amb els quals volem treballar. Finalment, cal implementar alguna **representació informàtica** concreta dels conceptes abstrets durant la fase anterior, per tal de poder-hi treballar fent servir les tecnologies que ens ofereixen les bases de dades i, també, els seus sistemes gestors.

1. El <span style="font-size:1.25em; text-decoration:underline;">**Món real**</span>. Està constituït pels **objectes (materials o immaterials) de la realitat que ens interessen** i amb els quals haurem de **treballar**.
1. El <span style="font-size:1.25em; text-decoration:underline;">**Món conceptual**</span>. És el conjunt de **coneixements, informacions, conceptes, ...** obtinguts gràcies a l'observació de la part del ***món real*** que ens interessa. Un mateix ***món real pot donar lloc a diferents mons conceptuals, en funció de la manera de percebre la realitat, o els interessos de l'observador d'aquesta*** .
1. El <span style="font-size:1.25em; text-decoration:underline;">**Món de les representacions**</span>. Està format per les **representacions informàtiques, o dades, del món conceptual, necessàries per poder treballar**.

![Figura 1. 1. **Els tres móns**](../images/ic10m2u1_01.png "Figura 1.1. Els tres móns")

[Figura 1. 1. **Els tres móns**](../images/ic10m2u1_01.png "Figura 1.1. Els tres móns.")

### 1.1. La realitat: **els objectes**.

Com a informàtics que hem d'analitzar o construir un sistema d'informació (<span style="font-size:1.25em; text-decoration:underline;">**SI**</span>) determinat, ens cal conèixer el món real al qual aquest <span style="font-size:1.25em; text-decoration:underline;">**SI**</span> ha de fer referència o modelitzar; així, el nostre **món real** podrà ser un *hospital*, una *empresa distribuïdora de productes alimentaris*, la *matriculació dels alumnes d'una universitat*, etc.

El **món real**, la part de la realitat que ens interessa, és el que percebem amb els nostres sentits i és compost per objectes concrets, físics o no.

* El *malalt* que es diu **Joan Garcia**,
* El *llit* número **34** de la **segona** *planta*,
* El *magatzem* ubicat a **Sòria**,
* El *camió* amb matrícula **3452-BFG**,
* L'*alumna* que es diu **Judith Pi**,
* L'*assignatura* de **Química I**,
* La *malaltia* anomenanda **meningitis**,
* La *devolució* d'**una comanda** concreta,
* L'*accident de trànsit* de **15 de gener** ocurregut a l'*autopista* **AP-7**,

són alguns exemples d'objectes que pertanyen al **món real**.

Com que treballem en el camp dels **SI**, els **mons reals** que ens interessen són les **organitzacions**: empreses, institucions, etc.

## 1.1.1 Les dades i la seva representació
Un cop estructurats, els conceptes entorn de la realitat passen a ser veritables informacions, amb les quals els humans ens podem comunicar i començar a treballar.
Però encara cal donar un altre pas que ens permeti representar aquestes informacions, de tal manera que les puguem tractar informàticament mitjançant BD i aplicacions, i aprofitem així tot el potencial de les noves tecnologies.

Les **dades** són representacions informàtiques de la informació disponible, relativa als objectes del món real del nostre interès.
El **món de les representacions** està format per les dades informatitzades amb les quals treballem.

Ara bé, la conversió de les concepcions en dades no és automàtica, ni de molt.
Requereix passar per dues fases successives de disseny, en què es prenen decisions que poden derivar en resultats dispars. Aquestes dues fases de disseny són les següents:
1. Fase de disseny lògic. Es treballa amb el model abstracte de dades obtingut al final de l'etapa de disseny conceptual, per tal de traduir-ho al model de dades utilitzat pel SGBD amb el qual es vol implementar i mantenir la futura BD.
1. Fase de disseny físic. Es poden fer certes modificacions sobre l'esquema lògic obtingut en la fase de disseny anterior, per tal d'incrementar l'eficiència en algunes de les operacions que s'hagin de fer amb les dades.
Per tant, cal ser conscients que, en un mateix conjunt de coneixements entorn d'una mateixa realitat, aquests es poden representar de maneres diferents a causa, per exemple, dels factors següents:
     Les decisions de disseny preses (tant a nivell conceptual, com a nivell lògic i físic).
     La tecnologia emprada (fitxers, BD relacionals, BD distribuïdes, etc.).
La possibilitat que hi hagi aquestes diferències no implica que tots els resultats es puguin considerar equivalents, sense més ni més, ja que, normalment, les representacions diferents donen lloc a nivells d'eficiència també diferents. Aquest fet pot tenir conseqüències importants, ja que la responsabilitat de tot informàtic inclou garantir la correcció de les representacions, però també l'eficiència de les implementacions.




