---
title: Principy kvantových výpočtů
description: Co jsou kvantové počítače a jak využívají principy kvantové mechaniky?
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
ms.openlocfilehash: 65fa85a80021124444fd352f9492d03cbefcb859
ms.sourcegitcommit: a03d79ca3f0774161a9f86a15528d36e1291acce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83433006"
---
# <a name="understanding-quantum-computing"></a>Principy kvantových výpočtů

Kvantové počítače využívají při zpracovávání informací principy kvantové mechaniky. Kvůli tomu kvantové výpočty vyžadují jiný přístup než ty klasické.  Jedním z příkladů těchto rozdílů je procesor používaný v kvantových počítačích.  Zatímco klasické počítače používají elektřinu a dobře známé čipy na bázi křemíku, kvantové počítače pracují s kvantovými stavy objektů jako atomy, ionty, fotony nebo elektrony.  

Kvantové objekty se chovají v souladu se zákony kvantové mechaniky, která využívá koncepty jako pravděpodobnostní výpočty, superpozice a provázání. Tyto koncepty poskytují základ pro kvantové algoritmy, které zapojují sílu kvantových výpočtů do řešení složitých problémů. Tento článek popisuje některé ze základních konceptů kvantové mechaniky, na kterých jsou kvantové výpočty založeny.

## <a name="a-birds-eye-view-of-quantum-mechanics"></a>Stručný přehled kvantové mechaniky

Kvantová mechanika, nebo také kvantová teorie, je větev fyziky, která se zabývá částicemi na atomické a subatomické úrovni. Na kvantové úrovni přestává platit většina zákonů klasické fyziky, na které jsme zvyklí. Superpozice, kvantové měření a provázání jsou tři jevy, které tvoří základy kvantových výpočtů.  

### <a name="superposition-vs-binary-computing"></a>Superpozice a kvantové výpočty

Představte si, že cvičíte ve svém pokoji. Otáčíte se kam až to jde doleva a pak zase doprava. A teď se zkuste otočit doleva a doprava současně. Asi to nepůjde (tedy pokud se nerozdvojíte).  Samozřejmě nemůžete být v obou těchto stavech najednou – nemůžete být otočení doleva i doprava zároveň.

Pokud jste ale subatomickou částicí, můžete s nějakou pravděpodobností směřovat *doleva* a SOUČASNĚ s nějakou pravděpodobností směřovat *doprava* díky jevu, který se označuje jako **superpozice** (někdy také jako **koherence**).

Částice, jako je například elektron, má své vlastní vlastnosti srovnatelné s „natočením doleva nebo doprava“, například **spin**, směřující zjednodušeně řečeno nahoru nebo dolů, nebo (v zájmu přiblížení ke klasickým počítačům) označovaný jako 1 nebo 0. Pokud je kvantová částice ve stavu superpozice, jedná se o libovolnou lineární kombinaci stavů 1 a 0, ale nevíte, který z obou stavů to nakonec bude, dokud se na částici nepodíváte. Tím se dostáváme k dalšímu důležitému jevu, kterým je **kvantové měření**.

### <a name="quantum-measurement"></a>Kvantové měření

Předpokládejme, že k vám přišel kamarád a chce si udělat fotku, jak cvičíte. Pravděpodobně by získal jen rozmazaný obrázek toho, jak se otáčíte někde mezi levou a pravou krajní polohou.

Pokud byste ale byli kvantová částice, stala by se zajímavá věc. Bez ohledu na vaši polohu v okamžiku, kdy kamarád mačká spoušť, budete na fotce vždy buď úplně nalevo, nebo úplně napravo – nic mezi.

Je to proto, že samotná akce změření kvantové částice **zkolabuje** její superpozici stavů (což se také označuje jako **dekoherence**) a částice získá klasický binární stav, buď 1, nebo 0.

Tento binární stav je pro nás užitečný, protože s jedničkami a nulami se dá ve světě výpočtů dělat spousta věcí. Jakmile je však částice změřena a zkolabovala její superpozice stavů, zůstane v tomto stavu natrvalo (stejně jako vaše fotka) a bude už stále představovat buď 1, nebo 0. Jak ale uvidíte později, v kvantových výpočtech se používají operace, které částici „resetují“ zpět do superpozice stavů, aby byla opět použitelná pro další kvantové výpočty.

### <a name="entanglement"></a>Provázání

Asi nejzajímavější jev kvantové mechaniky je schopnost dvou nebo více kvantových částic **provázat se** jedna s druhou. Provázané částice tvoří jediný systém, ve kterém se kvantový stav kterékoli z části nedá popsat nezávisle na kvantovém stavu ostatních částic. To znamená, že jakákoli operace nebo proces, který použijete u jedné částice, koreluje s ostatními částicemi.

Kromě této vzájemné závislosti platí, že částice udržují toto propojení i tehdy, když je dělí velké vzdálenosti, třeba i světelné roky. Účinky kvantového měření se vztahují i na provázané částice, to znamená, že když je jedna částice změřena a zkolabuje její superpozice stavů, druhá částice ve stejném okamžiku zkolabuje do jednoho stavu také. Díky korelaci mezi provázanými qubity poskytuje změření stavu jednoho qubitu informaci o stavu druhého qubitu – tato konkrétní vlastnost je při kvantových výpočtech velmi užitečná.

### <a name="qubits-and-probability"></a>Qubity a pravděpodobnost

Klasické počítače ukládají a zpracovávají informace po bitech, které můžou mít stav buď 1, nebo 0, ale nikdy ne obojí. Ekvivalentem bitů v kvantových výpočtech je **qubit**, který představuje stav kvantové částice. Díky superpozici může qubit nabývat stavu 1, 0 a čehokoli mezi tím. V závislosti na konfiguraci má qubit *určitou pravděpodobnost*, že zkolabuje do stavu 1 nebo 0. Pravděpodobnost kolapsu qubitu do jednoho nebo druhého stavu je dána **kvantovou interferencí**. 

Vzpomínáte si na kamaráda, který vás přišel vyfotit? Předpokládejme, že má na fotoaparátu speciální *interferenční* filtr. Pokud si vybere filtr *70/30* a začne fotit, na 70 % snímků budete směřovat doleva a na 30 % budete směřovat doprava. Filtr ovlivnil normální funkci fotoaparátu tak, že změnil pravděpodobnost výsledku.

Podobně i kvantová interference ovlivňuje stav qubitu tím, že mění pravděpodobnost určitého výsledku měření. Je to právě tento pravděpodobnostní stav, ve kterém kvantové výpočty excelují.

Například dva bity v klasickém počítači můžou každý uchovávat hodnotu 1 nebo 0, takže společně pojmou čtyři možné hodnoty – **00**, **01**, **10** a **11** – ale v každém okamžiku vždy pouze jednu z nich. U dvou qubitů v superpozici je však možné, že každý qubit může mít hodnotu 1 nebo 0 nebo *obojí*, takže dvojice qubitů může tyto čtyři hodnoty reprezentovat současně. Se třemi qubity můžete reprezentovat osm hodnot, se čtyřmi šestnáct a tak dále.

## <a name="summary"></a>Souhrn

Tyto koncepty jen kloužou po vnější slupce kvantové mechaniky, jsou však zásadně důležité pro pochopení kvantových výpočtů.

- **Superpozice** – schopnost kvantových částic nacházet se v kombinaci několika možných stavů současně.
- **Kvantové měření** – akt změření stavu kvantové částice v superpozici a stanovení jednoho ze dvou výsledných stavů, který se již nemění.
- **Provázání** – schopnost kvantových částic vzájemně korelovat výsledky svých měření.
- **Qubit** – základní jednotka informace v kvantových výpočtech. Qubit reprezentuje kvantovou částici v superpozici všech možných stavů.
- **Interference** – chování qubitu vyplývající z jeho podstaty. Díky superpozici stavů je možné ovlivňovat pravděpodobnost kolapsu superpozice do jednoho z možných výsledků.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Kvantové počítače a kvantové simulátory](xref:microsoft.quantum.overview.simulators)
