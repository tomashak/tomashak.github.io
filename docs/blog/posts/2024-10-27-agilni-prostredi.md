---
tags:
  - automatizace
  - agile
  - scrum
date:
  created: 2024-10-27
  last_modified: 2024-10-28
---

# Testing v agilním prostředí

Článek původně publikován na Tesena blogu: [Testing v agilním prostředí](https://www.tesena.com/testing-v-agilnim-prostredi/a-390/) 

Přibývá projektů, které chtějí investovat do efektivnějšího testování a používají tak automatizované testy. V tomto článku se dozvíte, jak přistoupit k automatizaci databázových testů.
Celá řada firem se v poslední době svezla na vlně a svůj vývoj přesunula z vodopádového modelu na agilní metodiky, nejčastěji Scrum či Kanban. Nebudeme zde hodnotit, zda-li to je dobře a co je lepší. Na toto téma existuje mnoho článků a videí, zmínil bych možná pro zajímavost záznam setkání pražských testerů, kde se uskutečnil pomyslný souboj obou přístupů a dres vodopádu tehdy cvičně oblékl i Marcel Veselka od nás z Teseny. Více informací naleznete [zde](https://www.pro-test.info/protest-75/).

Tesena poskytuje služby v oblasti testingu již řadu let a za tuto dobu jsem se svými kolegy zažil na mnoha projektech různé přístupy k testování v agilním světě a rád se o ně s vámi v následujících řádcích podělím. V obecné rovině bych je mohl rozdělit do 3 částí, které si v dalších kapitolách postupně popíšeme. Jedná se o personální přístup, technologický přístup a o přístup k plánování. V tomto čánku se zaměříme také na:

* Testování v agilním prostředí
* Principy agilního vývoje
* Definice vymezených rolí dle SCRUM metodiky
* Povahu jednotlivých typů ceremonií
* Přínos agilního vývoje pro testování
*  Možné komplikace a jejich řešení

## Pár slov obecně o agilním vývoji

Ještě než 3 body zmíněné v úvodu rozebereme detailně, rád bych se zmínil o základních principech agilního vývoje, konkrétně o Agilním manifestu.

### Základní principy

Mezi základní principy patří tyto body:

*    Software je dodáván často a průběžně
*    Jsou vítané změny, které pomůžou zákazníkovi
*    Fungující software je přednější než rozsáhlá dokumentace
*    Základní jednotkou jsou samoorganizující se týmy, které tvoří motivovaní členové
*    Je věnována pozornost technické vyspělosti a dobrému designu na začátku procesu
*    Spolupráce vývoje a byznysu po celou dobu produktu

### Role

V agilní metodice SCRUM je definován seznam jasně vymezených rolí. V krátkosti je lze popsat takto:

*    **Product Owner** vlastní vyvíjený produkt. Zřetelně definuje vizi, priority, pořadí úkolů a byznys logiku. Je zodpovědný za backlog, pravidelně provádí prioritizaci, případně některé úkoly odstraňuje.
*    **Scrum Master** eliminuje problémy, tlumí konflikty, motivuje developery a stará se, aby měli klid na práci. Dále hlídá dodržování procesu a jeho nutné změny. Pomáhá s udržováním flow v nástrojích pro správu úkolů (např. JIRA). Spolupracuje s Product Ownerem na řešení formální stránky nových úkolů tak, aby obsahovaly veškeré náležitosti.
*    **Development team** (QA, UI, Devs) řeší jednotlivé úkoly a vyvíjí produkt. Zavazuje se dodat určité úkoly v daném sprintu. Optimálně by měl mít do 10 členů. U větších týmů se doporučuje rozdělení na menší celky. V ideálním světě se složení týmu může měnit v závislosti na povaze úkolů, které jsou plánovány na nejbližší sprinty.
*    **Project Manager**: Prodává/prezentuje výsledky týmu dále. Koordinuje práci více Product Ownerů.

### Ceremonie

Uvedené role tvoří samoorganizující se tým (někde se používá termín „firma ve firmě“), který vyvíjí nějaký produkt v krátkých časových úsecích. Typicky se jedná o dvoutýdenní sprinty. Během sprintu se konají některé schůzky, kterým se v agilním světě říká ceremonie. Pravděpodobně jste se s nimi setkali. Patří sem:

#### Denní status (také se používá stand-up)
*    Účastní se ho vývojový tým, Scrum Master a volitelně i produktový vlastník
*    Bývá nejčastěji ráno, než všichni začnou pracovat
*    Neměl by trvat déle než 15 minut, v závislosti na velikosti týmu
*    Každý z členů by měl ostatním sdělit, co za předchozí den dokončil, na čem bude dělat dnes, zda předpokládá, že to dokončí, a také, zda má nějaké překážky a případně kdo mu s tím může pomoci
*    Často se volí varianta, kdy všichni stojí např. u TV v kanceláři, kde se zobrazuje board daného sprintu. Oproti pohodlnému sezení v zasedacích místnostech to tým alespoň nutí se tolik nerozpovídat. Někde jdou do extrémů a člověk, který mluví třeba i zároveň provádí různé cviky.
*    Některé firmy zavedou pouze tyto ranní statusy a považují to za známku agilního vývoje.
#### Grooming (ve volném překladu „odblešování“)
*    Účastní se ho Product Owner a vývojový tým
    Nemá pevné místo v rámci sprintu, tato schůzka se vytváří většinou v okamžiku, když je dostatek nových úkolů k ohodnocení
*    Délka schůzky je v přímé úměře k množství a velikosti úkolů. Většinou trvá 1-3 hodiny.
*    Hodnotí se náročnost vybraných úkolů z backlogu (ideálně nějaká ucelená množina)
*    Product owner celý úkol nejprve představí a detailně popíše, co od toho očekává za výsledky. Pokud to ještě není, doplní se k úkolu akceptační kritéria a další informace.
*    Vývojový tým o tom diskutuje, aby odhalili případné komplikace, nutné spolupráce jiných týmů nebo nutnost zásahu do dalších systémů.
    Nakonec se ohodnotí náročnost daného úkolu. Zde záleží na tom, jak si to daný tým nastaví. Někde používají tzv. člověkodny (MDs), jinde story pointy (1, 2,3, 5, 8, 13...) nebo třeba velikosti triček (XS, S, M, L, XL).
    Výsledkem je předpřipravený backlog, na kterém se v příštím sprintu dá začít vyvíjet.
#### Retrospektiva
*    Účastní se celý tým, včetně Scrum Mastera, který by tuto schůzku měl moderovat, což je zvláště zde důležité
*    Probíhá typicky v poslední den sprintu, nebo na začátku následujícího sprintu
*    Typicky trvá 1-2 hodiny podle velikosti týmu
*    Každý z účastníků zhodnotí, co se týmu jako celku povedlo, nepovedlo a co by chtěl zlepšit
*    Všechny tyto nápady se lepí/píšou na tabuli (případně i v elektronické verzi, pokud je část týmu na home office)
*    Následně každý dostane 3 body a oboduje, který nápad považuje za nejdůležitější nebo nejzávažnější
*    Následně celý tým diskutuje o těch nápadech, které dostaly nejvíce bodů
*    Výsledkem by mělo být nějaké řešení, nebo seznam úkolů, které jsou přiřazené konkrétním lidem
*    Při další retrospektivě se hodnotí plnění těchto úkolů
*    Retrospektiva by měla být v maximální možné míře konstruktivní a směřovat ke zlepšování týmu jako celku
#### Planning
*    Účast Product Ownera není povinná
*    Probíhá v závěru sprintu, často poslední den a je s retrospektivou spojen do jednoho bloku
*    Vývojový tým si ze seřazeného a ohodnoceného backlogu vybírá úkoly, které se zaváže dodat v následujícím sprintu
*    Většinou se vychází z předchozí průměrné rychlosti. Do výpočtu se zahrnou i plánované dovolené, svátky apod.
*    Úkoly se vybírají z backlogu shora dolů, pořadí určuje Product Owner a tím ovlivňuje, co požaduje dodat
*    Na této schůzce se také zavírá stávající sprint. Neuzavřené úkoly přepadávají do dalšího sprintu a tým si je doplní novými úkoly
*    Pokud je vše připraveno, tato schůzka nemusí přesáhnout půl hodiny
*    Součástí je i definování cílů následujícího sprintu
*    Tyto cíle jsou pak vždy připomínány na denních statusových schůzkách a tým si tím připomíná, zda je schopen cíle naplnit
#### Sprint review (někdy též demo)
*    Kromě týmu by se měli zúčastnit všichni, kterým tým dodal nějaké změny nebo nové funkce (stakeholdeři)
*    Schůzka bývá na konci sprintu
*    Tým se domluví, jestli se v prezentování budou členové střídat, nebo vše odprezentuje pouze jeden člověk
*    Tým prezentuje pouze věci, které zvládnul dokončit/uzavřít. Je vhodné, když se tým před schůzkou krátce sejde a definuje si, co vše se bude prezentovat.
*    Neprezentují se interní úkoly, například refaktoring, práce na technickém dluhu apod.
*    Vždy by mělo zaznít, která funkce se vyvinula/opravila, proč se to dělalo a komu to přinese užitek
*    Pokud lze, doporučuje se prezentaci nahrávat a následně archivovat
*    Na konci schůzky je prostor pro otázky stakeholderů

## Co přinesl agilní vývoj pro testing?

Dříve probíhal vývoj jinak, než je běžné dnes. Předně release probíhal jen několikrát ročně. Všechny fáze byly načasované, tedy ze začátku se ze zadání vytvářela analýza celého řešení, včetně všech dopadů. Začala se připravovat dokumentace a současně i tým testerů si dával dohromady testovací případy, které bude nutné připravit. Teprve v okamžiku, kdy vývojáři aplikaci dokončovali, začali všichni testeři testovat a reportovat chyby. Jednotlivé role zde byly zastoupeny jako celé týmy lidí, to znamená, že například i testování provádělo vždy více lidí současně a měli nad sebou test manažera, který je řídil, rozděloval práci a komunikoval s jinými týmy.

Přechodem na agilní vývoj se vše změnilo. Čas od zadání po release hotové funkce se řádově zkrátil. Na produkci se nasazuje i několikrát týdně po malých částech a nelze čekat na týdenní regresní manuální testování. Z toho plyne i větší snaha a motivace část testů **automatizovat** a ideálně i zařadit v **CI/CD** do procesu nasazování. Důležité je, že už přestaly existovat dedikované týmy vývojářů, testerů a analytiků. Vznikly samostatné týmy (firmy ve firmě), které měly typicky 3-6 vývojářů, jednoho analytika a jednoho až dva testery.  Týmy převzaly odpovědnost za své části aplikace, a ne jako dříve, za konkrétní fázi vývoje.

Upustilo se od rozsáhlých dokumentací a analýz. Produktový vlastník přišel s nápadem, co by v aplikaci chtěl naprogramovat. Analytik zjistil možné dopady do jiných aplikací, potřebná datová pole, která se posílají na backend, případně další informace nutné pro vývoj. Při groomingu už toto všechno je pak známo a je to součástí ticketu, ve kterém je zadání. Vývojáři si k úkolu přidají svoje informace, a i tester musí znát vše potřebné, aby to pak mohl co nejlépe otestovat. Samotné úkoly by měly být rozsahem velké maximálně na práci přes celý sprint. Pokud by to bylo náročnější, je nutné úkol rozdělit na menší úseky. Doporučuje se také celý task (nebo story) rozdělit na subtasky obsahující malé samostatné dílčí úkoly.

### Problém č. 1 – Plánování

Jak již bylo řečeno, už při plánování/groomingu bylo nutné myslet na všechny fáze a součástí pracnosti daného úkoly byl vždy i testing. Tester se musel na groomingu aktivně ptát, aby zjistil možné budoucí komplikace, které by například znemožnily dokončit celou funkcionalitu během sprintu. Na projektech se nám velmi osvědčilo si do úkolu přidávat testerské subtasky, např. pro přípravu testovacích dat/uživatelů, přípravu TC, opravu automatizovaných testů a pak i samotné manuální ověření. Část z toho bylo možné připravovat už dopředu a v okamžiku předání tasku od vývojářů na testing už byla část připravená.

Při samotném plánování byl problém s určováním náročnosti úkolu, respektive toho, jak bodovat. Na některých projektech se testing hodnotil zvlášť a pak se přičítal k hodnocení od vývojářů, nebo byla obě čísla společná. Za mě ale nejlépe fungoval přístup, kdy jsem hodnotil spolu s vývojáři. Představoval jsem si ten úkol komplexně, po čase jsme si vytvořili i vzorové Story pro 1, 2, 3, 5… bodů. Takže i tester pak dokázal náročnost určit podobně jako vývojář. Pouze v případě, že jsem věděl, že testování bude obsahovat velké množství práce, tak jsme v týmu výsledné číslo zvýšili například z 5 na 8, aby to reflektovalo náročnost testování. Na některých projektech se zaváděl i paralelní sprint a backlog pro testing, ale většinou se to neujalo, protože celý proces byl pak značně nepřehledný.

### Problém č. 2 – Složení týmu

V agilním světě fungují menší, samoorganizující se týmy. S tím souvisí i to, že na malé množství vývojářů se počítá většinou s jedním testerem. Neexistuje tu velký tým testerů řízený Test Managerem, který by na úkolech spolupracoval. První, co každého napadne, je určitě menší zastupitelnost. V případě dovolené nebo nemoci musí za testera někdo zaskočit. Většinou to je analytik nebo někdo z vývojářů. Je proto nutné, aby si tester udržoval kvalitní dokumentaci a např. přehled testovacích dat, který můžou ostatní členové týmu v případě jeho nepřítomnosti použít. S těmito daty a postupy pro testování aplikace je třeba celý tým pravidelně seznamovat.

Tester, pokud je takto sám v týmu, musí být tím, kdo by měl dovnitř týmu předávat základní myšlenky ohledně testingu. Je třeba i nastavit procesy během sprintu tak, aby se předešlo přetížení testera například na konci sprintu. Toho se dá docílit rozdělením větších úkolů na menší samostatné celky, kdy je tester může odbavovat postupně. Pokud je vhodné k nějaké nové funkci doplnit i automatizovaný test, lze jeho implementaci odložit na začátek následujícího sprintu, kdy bývá pro testing obecně méně práce a je tam pro toto prostor.

Pokud je dopředu známo, že tester třeba 2-3 týdny bude na dovolené, tak se vyplatí domluvit na planningu předem a do sprintu naplánovat úkoly, kde se nepředpokládá rozsáhlé testování a ověřit si, jak to zvládnou vývojáři mezi sebou. Do daného úkolu se do poznámek může připsat checklist případů, které tester doporučuje projít, aby se na nic nezapomnělo.

### Problém č.3 – Technické přístupy

S předchozím souvisí i toto. Na většině agilních projektů je snaha řešit testy automatizovaně. Na to existuje velké množství nástrojů a frameworku prakticky ve všech používaných programovacích jazycích. Jako testeři bychom si tedy vybírali podle účelu a podle typu aplikací, které budeme chtít testovat. Bude tedy rozhodovat primárně to, zda v daném nástroji chceme řešit testy pouze API, nebo kombinovaně s webovou aplikací, jestli se bude jednat pouze o funkční testy, nebo bychom rádi i testovali performance apod.

Na mnoha projektech, kde jsme spolu s kolegy z Teseny byli, jsme museli při výběru nástroje přihlédnout k tomu, co používali vývojáři a také v čem programovali. Je totiž důležité počítat s tím, že automatizaci budou řešit prakticky všichni v týmu, protože pokud jediný tester v týmu onemocní nebo je na dovolené, tak je nutné, aby existovala jeho zastupitelnost. Pokud tedy v týmu jsou pouze PHP vývojáři, můžeme s úspěchem použít framework Codeception právě v tomto jazyku, případně čisté PHP s knihovnami pro Selenium. Podobně se můžeme přizpůsobit Java programátorům, stejně tak i pro Javascript a Python existuje velké množství možností.

Z vlastní zkušenosti mohu říct, že vývojáři často nemají představu o funkci automatizovaných testů, nebo jen mlhavě tuší. Pokud pro ně připravíme hodinovou ukázku, včetně rozebrání zdrojového kódu, živého spuštění testů a kontroly jejich výsledků, ve většině případů se pro to nadchnou a sami navrhují, že by s psaním testů pomáhali. Má to několik výhod. Předně se jedinému testerovi částečně uvolní ruce, protože bude vývojář schopný si základní testy na vyvíjenou funkci napsat sám. Další scénáře, předně ty negativní, pak stále zůstanou na testerovi. On by měl znát všechny možné scénáře, které můžou nastat a pokud to lze, aby bylo vše pokryto testy. Další výhoda je to, že si tester a vývojář vzájemně můžou dělat revize kódu automatizovaných testů. Tester má tak možnost zlepšit svoji kvalitu kódu, vyvarovat se běžných nešvarů a obecně psát svůj kód čitelnějším způsobem. Pokud už takto vývojáři i testeři zvládají spolupracovat, většinou sami vývojáři začnou navrhovat, jak např. webovou aplikaci upravit, aby byla snáze automatizovatelná. Může se jednat o snahu doplnit ID k elementům na stránce, doplnit Javascript, který dokáže informovat, že je stránka kompletně načtená, nebo pomůžou zpřístupnit pomocné systémy na pozadí pro automatizované testy. Testy pak můžou využívat např. číselník textů jednotlivých elementů v různých jazycích, zakládat si data/uživatele pomocí API na backendu, nebo si některé výsledky ověřovat v DB apod. Testy se pak stanou komplexnějšími a do jisté míry i stabilnějšími.

Nyní tedy uvažujeme situaci, kdy vývojáři pomáhají s psaním automatizovaných testů. Stále je ale tester ten člověk, který by měl kontrolovat jejich běh, typicky výsledek nočního spouštění a v případě chyb analyzovat, co se stalo a jestli je třeba opravit testy, nebo zadat novou chybu. Prvním problémem je místo, kde testy běží. Ve většině případů se jedná o Jenkins (či jiný CI/CD nástroj), který je samostatnou instancí čistě jen pro pouštění testů a na svých nodech má nainstalované potřebné knihovny. Tester je samozřejmě zvyklý report kontrolovat, ale pro vývojáře to může být jen dalším ze systémů, kam musí chodit a mít tam přístup. Řešením je zde zakomponovat spouštění testů na stejné místo, kde se buildí nebo nasazují aplikace na testovací prostředí. Nasazení nové verze aplikace pak na pozadí může rovnou spustit testy. Nebo z našich testů vyčlenit sadu smoke testů, které budou trvat krátký časový úsek a zařadit jejich spouštění přímo do pipeline nasazování.

Stejně jako způsob samotného spouštění testů je neméně důležitý i formát výsledku. Nástroje pro automatizaci většinou nabízí vlastní způsob reprezentace výsledku běhu, každopádně ne vždy takový formát musí vyhovovat a je třeba přemýšlet i o tom, jak výsledky co nejvíce přiblížit ostatním členům v týmu, aby měli okamžitý přehled, co se s aplikací děje a co přestalo fungovat. Nedávno jsem na toto téma publikoval článek.

# Závěr

Co říci závěrem? Agilní přístup ve vývoji SW neznamenal jen zrychlení samotného vývoje, ale změnilo se i celkově testování. Testují se malé změny v aplikaci, současně je třeba testovat i regresně, zda změna nezpůsobuje chybu v jiné části. Z toho důvodu se klade větší důraz na automatizaci a CI/CD. Rozdíly v týmu mezi vývojáři a testery se zmenšují. Každý má stále svou oblast působnosti a nový přístup současně umožňuje vzájemnou spolupráci, revize a výpomoc. Pro testera to znamená nutnost přizpůsobení se, protože na testing bývá v týmu většinou sám. Často se tak zaměří na výběr takových nástrojů, které budou vyhovovat i vývojářům. Se všemi výzvami jsme se na projektech v Teseně úspěšně poprali. Pokud byste rádi věděli detaily, určitě nám napište a můžeme vše probrat u kávy.
