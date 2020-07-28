<h1 style="font-size: 2.5em; padding-bottom: .3em; border-bottom: 2px solid #eaecef;">UF01: Introducció a les bases de dades</h1>

Actualment estem absolutament envoltats d'**informació** la qual, en el **99%** de les vegades està emmagatzemada en una **base de dades**.

Les dades que s'utilitzen en els **sistemes d'informació** (<code style="font-size:2em; text-decoration:underline;">**SI**</code>) s'acostumen a emmagatzemar en **bases de dades** (<code style="font-size:2em; text-decoration:underline;">**BD**</code>). Per a poder parlar i raonar amb certa propietat sobre les <code style="font-size:1.25em;">**BD**</code>, ens convindrà tenir clar què són <span style="font-size:1.25em; text-decoration:underline;">les **dades**</span>, que és <span style="font-size:1.25em; text-decoration:underline;">la **informació**</span>, i quines són <span style="font-size:1.25em; text-decoration:underline;">les **abstraccions**</span> que els informàtics representem físicament sobre discs magnètics, CD-ROM, cartutxos de cinta, etc. Amb aquest objectiu, haurem d'adquirir algunes nocions teòriques fonamentals i disposar d'eines formals en què basar-nos.

Tot informàtic que hagi de treballar amb **bases de dades** (```BD```), és imprescindible que sàpiga distingir tres àmbits ben diferenciats, però que al mateix temps estan fortament interrelacionats, els quals fan referència, respectivament, a la **realitat**, a la seva **conceptualització**, i a la seva **representació informàtica**.

Anomeneu exemples diaris en què creieu que hi ha informació emmagatzemada en una base de dades.
1. Treure calers d'un caixer automàtic.
1. ...

Per tant, com a tècnics superiors en informàtica, cal que tingueu molt clars tot un seguit de conceptes relacionats amb les **dades** i de la seva **representació informàtica**.

Per començar cal entendre que hi ha tres àmbits que hem de ser capaços de diferenciar per tal de treballar correctament amb les dades: <span style="font-size:1.25em; text-decoration:underline;">el **món real**</span> amb els objectes del nostre interès, <span style="font-size:1.25em; text-decoration:underline;">el **món conceptual**</span> que conté el conjunt dels coneixements obtinguts observant el **món real** i <span style="font-size:1.25em; text-decoration:underline;">el **món de les representacions**</span> que no deixen de ser representacions físiques dels coneixements que tenim dels objectes del **món real**.

## 1. Els tres mons: el **real**, el **conceptual** i el de les **representacions**.

Per **món real**, s'entén la part de la realitat (sigui tangible o intangible) que en un moment determinat ens interessa informatitzar perquè hem rebut un encàrrec en aquest sentit. 
Així doncs, mitjançant l'observació de la realitat, s'obté un conjunt d'abstraccions de les informacions considerades rellevants, es construeix un **model que conceptualitza** els aspectes de la realitat amb els quals volem treballar. Finalment, cal implementar alguna **representació informàtica** concreta dels conceptes abstrets durant la fase anterior, per tal de poder-hi treballar fent servir les tecnologies que ens ofereixen les **bases de dades** i, també, els seus sistemes gestors.

1. El <span style="font-size:1.25em; text-decoration:underline;">**Món real**</span>. Està constituït pels **objectes (materials o immaterials) de la realitat que ens interessen** i amb els quals haurem de **treballar**.
1. El <span style="font-size:1.25em; text-decoration:underline;">**Món conceptual**</span>. És el conjunt de **coneixements, informacions, conceptes**..., obtinguts gràcies a l'observació de la part del ***món real*** que ens interessa. Un mateix ***món real pot donar lloc a diferents mons conceptuals, en funció de la manera de percebre la realitat, o els interessos de l'observador d'aquesta*** .
1. El <span style="font-size:1.25em; text-decoration:underline;">**Món de les representacions**</span>. Està format per les **representacions informàtiques, o dades, del món conceptual, necessàries per poder treballar**.

![Figura 1.1. **Els tres mons.**](../images/ic10m2u1_01.png "Figura 1.1. Els tres mons.")

[Figura 1.1. **Els tres mons.**](../images/ic10m2u1_01.png "Figura 1.1. Els tres mons.")

### 1.1. La *<span style="text-decoration:underline;">realitat</span>*: els **objectes**.

Com a informàtics que hem d'analitzar o construir un **sistema d'informació** <span style="font-size:1.25em; text-decoration:none;">**(SI)**</span> determinat, ens cal conèixer el **món real** al qual aquest <span style="font-size:1.25em;">**SI**</span> ha de fer referència o modelitzar; així, el nostre **món real** podrà ser un *hospital*, una *empresa distribuïdora de productes alimentaris*, la *matriculació dels alumnes d'una universitat*, etc.

El **món real**, la part de la realitat que ens interessa, és el que percebem amb els nostres sentits i és compost per objectes concrets, físics o no.

* El ***```malalt```*** que es diu **```Joan Garcia```**,
* El ***```llit```*** número **```34```** de la **```segona```** ***```planta```***,
* El ***```magatzem```*** ubicat a **```Sòria```**,
* El ***```camió```*** amb matrícula **```3452-BFG```**,
* L'***```alumna```*** que es diu **```Judith Pi```**,
* L'***```assignatura```*** de **```Química I```**,
* La ***```malaltia```*** anomenada **```meningitis```**,
* La devolució de la ***```comanda```*** amb número **```BN-1234```**,
* L'***```accident de trànsit```*** ocorregut el **```15 de gener```** a l'***```autopista```*** **```AP-7```**,

són alguns exemples d'objectes que pertanyen al **món real**.

Com que treballem en el camp dels **SI**, els **mons reals** que ens interessen són les **organitzacions**: *empreses*, *institucions*, etc.

### 1.2. Les *<span style="text-decoration:underline;">concepcions</span>*: la **informació**.

Observant el **món real**, els humans som capaços de deduir-ne **coneixements**, **informació**. L'observació dels objectes del **món real** ens porta a fer-ne l'*anàlisi* i la *síntesi*; després, n'obtenim **abstraccions**, en fem *classificacions* (podem saber que dos objectes són de la mateixa classe malgrat que siguin diferents), en deduïm **propietats** i **interrelacions**, etc.

Per exemple, l'observació del camp de la **matriculació en una universitat** ens permet reconèixer diferents *classes* o *tipus d'objectes*, com ara l'*alumne* o l'*assignatura*. Deduïm que *tot alumne* tindrà les *propietats* (són **abstraccions**) *data de naixement*, *DNI*, *nom*, etc. i així obtenim **informacions** com les següents: l'alumna de *nom* **Judith Pi** té el *DNI* **34.567.854** i el seu *any de naixement* és el **1979**.

El **conjunt dels coneixements** obtinguts observant un **món real**, l'anomenem **món conceptual** o **món de les concepcions**. En l'esfera de les concepcions construïm un **model abstracte**, **conceptual**, del **món real**, i això ens ajuda a raonar i a expressar-nos.

El procés d'**observació/abstracció** és bàsicament un procés per a **modelitzar** l'**estructura**, les **propietats** i el **funcionament de la realitat**.

De fet, hi ha diferències entre **coneixement** i **informació**. La **informació** és un **coneixement transmissible**, és a dir, que es pot **representar**. Els únics **coneixements** que ens **interessaran** aquí són, doncs, les **informacions**.

Un mateix **món real** pot ser vist, concebut, modelitzat, de maneres diferents per diferents observadors (fins i tot per un mateix observador) segons el seu **entorn** o **marc de referència**. Per exemple, no veu de la mateixa manera l'àmbit de la gestió d'un **centre universitari** un **professor** que un **administratiu de secretaria**. Tenen **marcs de referència** diferents. No estan interessats en els mateixos conceptes. El **professor**, a diferència de l'**administratiu**, no necessitarà conèixer l'**import de la matrícula**, no voldrà distingir les **abstraccions**, *alumne amb beca* i *alumne sense beca*. Els **professors** estaran interessats en la **qualificació numèrica**, mentre que el **servei administratiu** potser només tindrà en compte la **forma textual** de la **qualificació**.

Veiem, doncs, que en el pas del **món real** al de les **concepcions** hi ha **pluralisme**. L'**observació** i l'**anàlisi** d'una mateixa part d'una **organització** o **empresa** poden portar a **concepcions diferents**, totes igualment **vàlides** i que poden haver de **coexistir**.

### 1.3. Les *<span style="text-decoration:underline;">representacions</span>*: les **dades**.

El **món de les concepcions** o **món dels coneixements** és un *món mental*. Però per a poder treballar amb aquests **coneixements** i poder comunicar-los, necessitem *projectar* els pensaments a l'exterior *representant-los* físicament d'alguna manera. Aquest és el **món de les representacions**.

Aquí ens ocuparem de les **representacions informàtiques**, i parlarem de **dades**, **fitxers**, **bases de dades**, **registres**, **camps**, **bytes**, **discs**, etc.

Donem el nom de **dades** <span style="text-decoration:underline;">*a les representacions físiques dels coneixements que tenim dels objectes del ***món real***</span>*. El **pas** dels **coneixements a les dades**, el pas d'una concepció a una representació informàtica, **no és automàtic**. És un **procés humà**, un **procés de disseny**.

Òbviament, en aquest cas, com en el cas del pas del **món real** al **món de les concepcions**, també hi ha **pluralisme**. *Un mateix conjunt de coneixements es pot representar de moltes maneres*, per exemple: en forma de **base de dades relacional** o com a **fitxers tradicionals**, amb **vectors** o sense, de **longitud fixa** o de **longitud variable**, amb codificació **<span style="text-decoration:underline;">[ASCII](https://ca.wikipedia.org/wiki/ASCII)</span>** o **<span style="text-decoration:underline;">[EBCDIC](https://ca.wikipedia.org/wiki/EBCDIC)</span>**, etc.

Una visió o concepció del **món real** d'un **hospital**, d'una **universitat** o d'una **distribuïdora de productes** podrà ser representada de moltes maneres sobre suports **físics informàtics**. Es poden fer <span style="text-decoration:underline;">***molts dissenys diferents de representació informàtica corresponents a un únic model conceptual d'una realitat***</span>. Tots poden representar la mateixa realitat, però tindran una eficiència diferent segons la utilització que se'n faci.

Sense cap mena de dubte, les feines més importants de l'**analista**/**dissenyador** de **SI** o d'**aplicacions informàtiques** són les següents:

1. **Analitzar** els objectes del **món real**, fer-ne abstraccions i obtenir-ne una concepció lògica, un model conceptual.

1. **Dissenyar** una representació informàtica concreta que es pugui tractar eficientment.

El fet de *saber observar la realitat*, fer-ne les *abstraccions lògiques* més escaients, l'*habilitat* per a l'*anàlisi* i la *síntesi*, esdevenen les **qualitats fonamentals** que ha de tenir el desenvolupador de **SI**. I aquestes qualitats s'han d'educar i treballar.

El pas d'un **món conceptual** a un **món de representacions informàtiques** s'ha fet més senzill a mesura que la tecnologia informàtica avançava i se'n simplificava la utilització. Els anys seixanta i setanta el desenvolupador d'aplicacions es veia obligat a tenir en compte una multitud de detalls físics de la representació informàtica. Actualment, la simplificació del procés de disseny de la representació fa que el procés d'observació/abstracció esdevingui la tasca principal del desenvolupador de **SI**.

### 1.4. La **<span style="text-decoration:underline;">interpretació</span>**.

Acabem de veure el camí que ens porta de la **realitat** als **coneixements**, i dels **coneixements** a les **dades** o **representacions**. Però ens farà falta poder **interpretar la representació**. El procés invers al de **representació**, l'anomenem **interpretació**.

Si veiem una **dada**, una **representació** extreta d'una **base de dades** relativa a la *matriculació d'alumnes*, que consta de la sèrie de símbols: 1 9 9 9, no en podrem obtenir cap informació si no sabem si representa l'*any de matriculació*, l'*any de naixement*, l'*import de la matrícula*, el *número de la matrícula*, etc., i en qualsevol cas no sabrem de quin alumne concret (de quin objecte del **món real**) es tracta. Veiem, doncs, que per a poder **interpretar** les **dades** s'ha de saber, a més, a qui i a què (a quins **conceptes**) fan referència.

Hem dit que una **informació** és un <span style="text-decoration:underline;">*coneixement que es pot representar*</span>, però ara, mirant el camí invers, podrem dir que la **informació** és el <span style="text-decoration:underline;">significat que donem a les dades</span>.

***************

## 1.1.1 Les dades i la seva representació
Un cop estructurats, els conceptes entorn de la realitat passen a ser veritables informacions, amb les quals els humans ens podem comunicar i començar a treballar.
Però encara cal donar un altre pas que ens permeti representar aquestes informacions, de tal manera que les puguem tractar informàticament mitjançant ```BD``` i aplicacions, i aprofitem així tot el potencial de les noves tecnologies.

Les **dades** són representacions informàtiques de la informació disponible, relativa als objectes del **món real** del nostre interès.
El **món de les representacions** està format per les dades informatitzades amb les quals treballem.

Ara bé, la conversió de les concepcions en dades no és automàtica, ni de molt.
Requereix passar per dues fases successives de disseny, en què es prenen decisions que poden derivar en resultats dispars. Aquestes dues fases de disseny són les següents:
1. Fase de disseny lògic. Es treballa amb el model abstracte de dades obtingut al final de l'etapa de disseny conceptual, per tal de traduir-ho al model de dades utilitzat pel SGBD amb el qual es vol implementar i mantenir la futura ```BD```.
1. Fase de disseny físic. Es poden fer certes modificacions sobre l'esquema lògic obtingut en la fase de disseny anterior, per tal d'incrementar l'eficiència en algunes de les operacions que s'hagin de fer amb les dades.
Per tant, cal ser conscients que, en un mateix conjunt de coneixements entorn d'una mateixa realitat, aquests es poden representar de maneres diferents a causa, per exemple, dels factors següents:
     Les decisions de disseny preses (tant a nivell conceptual, com a nivell lògic i físic).
     La tecnologia emprada (fitxers, ```BD``` relacionals, ```BD``` distribuïdes, etc.).
La possibilitat que hi hagi aquestes diferències no implica que tots els resultats es puguin considerar equivalents, sense més ni més, ja que, normalment, les representacions diferents donen lloc a nivells d'eficiència també diferents. Aquest fet pot tenir conseqüències importants, ja que la responsabilitat de tot informàtic inclou garantir la correcció de les representacions, però també l'eficiència de les implementacions.


