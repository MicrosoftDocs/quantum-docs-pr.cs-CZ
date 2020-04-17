---
title: Co jsou kvantové výpočty?
description: Seznámení s hardwarem, algoritmy a funkcemi kvantových výpočtů a sadou Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 668df50882272bfa56541f178e2f4d5fb35efcf5
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906776"
---
# <a name="what-is-quantum-computing"></a>Co jsou kvantové výpočty?

Některé problémy jsou tak složité a tak neuvěřitelně obrovské, že i kdyby na řešení pracovaly všechny superpočítače na světě, trvalo by jeho nalezení déle, než bude existovat vesmír.

Kvantové počítače slibují vyřešení některých z největších výzev naší planety – v oblasti životního prostředí, zemědělství, zdraví, energetiky, klimatu, nauky o materiálech a problémů, které si ještě neumíme ani představit. Přínos kvantových počítačů bude dalekosáhlý a bude srovnatelný s důsledky vyrobení prvního tranzistoru v roce 1947, které připravilo cestu pro dnešní digitální ekonomiku.

Kvantové výpočty využívají jedinečné chování kvantové fyziky a přinášejí nový, výkonný výpočetní model. Teorie kvantové fyziky předpokládá, že hmota na kvantové úrovni může být v superpozici několika klasických stavů. A toto množství stavů se vzájemně ovlivňuje jako vlny v přílivovém jezírku.  Předpokládá se, že stav hmoty po změření „zkolabuje“ do jednoho z klasických stavů. 

Opakováním stejného měření se tedy dojde ke stejnému klasickému výsledku.  Ke kvantovému provázání dojde, když se částice vzájemně ovlivňují takovým způsobem, že jejich kvantový stav nelze popsat bez závislosti na ostatních, a to i v případě, že jsou fyzicky vzdálené.  

Při kvantových výpočtech se informace ukládají v kvantových stavech hmoty. Její kvantový charakter superpozice a provázání se využívá při kvantových operacích, které provádějí výpočty s těmito informacemi, a tím ovládají kvantovou interferenci a učí se ji programovat.

Kvantové výpočty se můžou jevit jako náročné, s těmi pravými prostředky však můžete začít vytvářet kvantové aplikace už dnes.

## <a name="the-qubit"></a>Qubit

Kvantové výpočetní prostředí definuje výpočetní koncepce, které odrážejí kvantové chování.  Kvantové výpočty začínají u pojmu qubit.  V kvantových výpočtech představuje kvantový bit (**qubit**) jednotku kvantových informací podobnou klasickému bitu. Zatímco klasické bity obsahují jednu binární hodnotu (tj. 0 nebo 1), qubit se může současně nacházet v **superpozici** stavů 0 a 1.  

Změřením qubitu se jeho stav změní. V důsledku změření přejde qubit ze superpozice do jednoho z klasických stavů.  

Několik qubitů může být také **provázáno**. Když změříme jeden provázaný qubit, změní se tím naše znalost stavu ostatních qubitů.

## <a name="quantum-algorithms"></a>Kvantové algoritmy

Kvantové algoritmy jsou navržené tak, aby využívaly kvantový charakter a chování k urychlení klasických algoritmů nebo aby přinášely zcela nové způsoby modelování fyzických systémů.  Tyto algoritmy využívají způsob, jakým se v qubitech kódují informace, a paralelní charakter práce s více provázanými qubity v superpozici.  

Klasické počítače kódují informace do bitů; v každém bitu můžou být zakódované dvě hodnoty: 0 nebo 1.  V jednom qubitu jsou současně zakódované dvě hodnoty: 0 a 1.  Dva klasické bity kódují jednu ze 4 možných hodnot (00, 01, 10, 11), zatímco dva qubity kódují každou superpozici těchto 4 stavů současně, ačkoli při měření můžeme zjistit jen jednu z těchto hodnot. Čtyři qubity kódují všechny superpozice 16 hodnot současně a tak dále (exponenciálně).  100 qubitů může zakódovat víc informací, než je dnes k dispozici v těch největších počítačových systémech.  

Když se navíc několik provázaných qubitů chová koherentně, můžou zpracovávat víc možností současně. Provázané qubity můžou zpracovat informace ve zlomku času, který by potřebovaly i ty nejrychlejší nekvantové systémy.

Ovládání těchto kvantových atributů je výsledkem několika desetiletí výzkumu kvantových algoritmů. Bylo nalezeno mnoho inovativních postupů, které řeší problémy za zlomek času potřebného k řešení klasickým způsobem.  

Jedním z nejznámějších kvantových algoritmů je _Shorův algoritmus_ pro rozklad, při jehož použití se klasicky neřešitelný problém rozkladu velkého čísla na dvě prvočísla řeší tak rychle, že to ohrožuje tradiční kryptografii.

Z konstruktivnějšího hlediska jsou díky superpozici, kvantovému provázání a vlastnosti **neklonování** qubitů (nemožnosti jejich nezjištěného kopírování) možné algoritmy bezpečné distribuce šifrovacích klíčů.

_Groverův algoritmus_ využívá techniku kvantového algoritmu, která dosahuje kvadratického zrychlení hledání v nestrukturovaných datech.

## <a name="quantum-hardware"></a>Kvantový hardware

V klasických počítačích odpovídají bity úrovním napětí v křemíkových obvodech. Hardware pro kvantové výpočty může být implementován v mnoha různých fyzických realizacích qubitů: uvězněné ionty, supravodivost, neutrální atomy, spin elektronů, polarizace světla, topologické qubity. Kvantový hardware je vznikající technologií. Qubity jsou křehkého charakteru a při interakci s prostředím se stávají méně koherentními. Je potřeba vyvážení míry věrnosti systému a škálovatelnosti. Čím větší je měřítko (počet qubitů), tím vyšší je chybovost.

Microsoft vyvíjí kvantový počítač založený na topologických qubitech. Věříme, že topologický qubit bude méně ovlivňován změnami v jeho prostředí, a tím se bude snižovat míra externích oprav chyb. Topologické qubity vykazují vyšší stabilitu a odolnost vůči šumu prostředí. To znamená, že je lze lépe škálovat a že déle zůstávají spolehlivé.

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a>Kvantové výpočty – plný hardwarový a softwarový zásobník

Kvantový program Microsoftu je jedinečný v tom, že se zaměřujeme na škálování každé komponenty systému, abychom dosáhli skutečného kvantového výsledku. Tento komplexní přístup zahrnuje:

* sestavení kvantového počítače se spolehlivými a škálovatelnými topologickými qubity odolnými vůči selhání, 
* vytvoření jedinečné kryogenické řídicí roviny s nízkými ztrátami výkonu a tepelnými ztrátami, 
* vývoj kompletního softwarového zásobníku, který umožňuje programování kvantového počítače a řízení systému ve velkém měřítku.

Opensourcová sada Quantum Development Kit (QDK) byla uvedena proto, aby zpřístupnila kvantové programování a vývoj algoritmů. Náš programovací jazyk vysoké úrovně Q# řeší výzvy kvantového programování.  Navrhli jsme Q# jako kvantově orientovaný programovací jazyk vysoké úrovně zaměřený na vývoj algoritmů a aplikací. Kompilátor jazyka Q# je integrovaný do softwarového zásobníku, který umožňuje zkompilování kvantového algoritmu až na úroveň primitivních operací kvantového počítače.  Do určitého rozsahu (počtu qubitů) je možné simulovat kvantové výpočty na klasickém počítači. S využitím simulace můžete už dnes začít psát kvantové programy, které se zítra budou spouštět na kvantovém hardwaru.  Navíc jsme pro jazyk Q# připojili ukázky, knihovny a studijní cvičení, abychom vám umožnili začít s kvantovým programováním už dnes. 

## <a name="next-steps"></a>Další kroky

* [Co dokážou kvantové počítače?](xref:microsoft.quantum.overview.computers)
* [Začínáme se sadou Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
* Přečtěte si další informace o [koncepcích kvantových výpočtů](xref:microsoft.quantum.concepts.intro)
