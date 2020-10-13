---
title: Kvantové počítače a kvantové simulátory
description: Přečtěte si o kvantovém hardwaru, kvantových simulátorech a o tom, jak fungují kvantové operace.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
no-loc:
- Q#
- $$v
ms.openlocfilehash: 714d8163a66feea2766a71886c6d07275098ac2f
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771355"
---
# <a name="quantum-computers-and-quantum-simulators"></a>Kvantové počítače a kvantové simulátory

Kvantové počítače jsou zatím stále ještě v plenkách. Hardware a údržba jsou nákladné a většina systémů se nachází ve vysokých školách a výzkumných laboratořích. Technologie se ale vyvíjí, a již je k dispozici omezený veřejný přístup k některým systémům.

Kvantové simulátory jsou softwarové programy spouštěné na klasických počítačích, které umožňují spouštět a testovat kvantové programy v prostředí, které předpovídá, jak budou qubity bude reagovat na různé operace.

## <a name="quantum-hardware"></a>Kvantový hardware

Kvantový počítač má tři hlavní části: oblast, ve které jsou uchovávány qubity, způsob přenosu signálů do qubitů a klasický počítač ke spouštění programů a odesílání instrukcí.

- Kvantové materiály používané pro uchovávání qubitů jsou vysoce citlivé na rušivé vlivy z okolního prostředí. Některé metody uchovávání qubitů pracují jen při teplotách těsně nad absolutní nulou, aby se maximalizovala jejich koherence. Jiné způsoby uchovávání qubitů používají vakuovou komoru, která minimalizuje vibrace a zajišťuje stabilitu.  
- Signály mohou být na qubity přenášeny s využitím nejrůznějších metod, včetně mikrovln, laserů nebo elektrického napětí.

Je třeba vyřešit ještě spoustu problémů, než budou moci kvantové počítače pracovat správně. Oprava chyb je v kvantových počítačích významný problém a škálování (přidávání qubitů) zvyšuje míru výskytu chyb. Z důvodu těchto omezení je kvantový stolní osobní počítač ještě hudbou daleké budoucnosti, ale komerčně využitelný laboratorní kvantový počítač je již blíže.

## <a name="quantum-simulators"></a>Kvantové simulátory

Kvantové simulátory spouštěné na klasických počítačích umožňují simulovat běh kvantového algoritmu na kvantovém systému.  Sada Quantum Development Kit (QDK) od společnosti Microsoft zahrnuje plnostavovou vektorovou simulaci i další specializované kvantové simulátory.

## <a name="topological-qubit"></a>Topologické qubity

Microsoft vyvíjí kvantový počítač založený na topologických qubitech. Topologický qubit bude méně ovlivňován změnami prostředí a díky tomu nebude vyžadovat tolik externích oprav chyb.

Topologické qubity vykazují vyšší stabilitu a odolnost vůči šumu prostředí. To znamená, že je lze lépe škálovat a že déle zůstávají spolehlivé.

## <a name="microsoft-and-quantum-hardware-partnerships"></a>Partnerství společnosti Microsoft v oblasti kvantového hardwaru

Společnost Microsoft spolupracuje s výrobci hardwarových kvantových počítačů IonQmi, Honeywell a QCI, aby byly v budoucnu přístupné vývojářům. Díky platformě Azure Quantum budou vývojáři moci používat sadu Quantum Development Kit (QDK) a jazyk Q# společnosti Microsoft k psaní kvantových programů a jejich vzdálenému spouštění.

## <a name="quantum-computations"></a>Kvantové výpočty

Výpočty na kvantovém počítači nebo kvantovém simulátoru probíhají v rámci tohoto základního procesu:

- Přístup k qubitům
- Inicializace qubitů do požadovaného stavu
- Provedení operací transformujících stav qubitů
- Změření nového stavu qubitů

Inicializace a transformace qubitů se provádí pomocí **kvantových operací** (někdy se jim říká kvantová hradla). Kvantové operace se podobají logickým operacím u klasických počítačů, jako jsou například AND, OR, NOT a XOR. Operací může být jednoduché převrácení stavu qubitu z 1 na 0 nebo provázání páru qubitů, až po použití série operací, které ovlivní pravděpodobnost kolapsu superpozice stavů qubitu do jednoho nebo druhého stavu.

> [!NOTE] 
> [Knihovny Q#](xref:microsoft.quantum.libraries) poskytují vestavěné operace definující složité kombinace nízkoúrovňových kvantových operací. Operace z knihovny můžete použít k transformaci qubitů a k vytvoření složitějších uživatelem definovaných operací.  

Měření výsledku výpočtu nám dá odpověď, ale u některých kvantových algoritmů ne nutně tu správnou. Vzhledem k tomu, že výsledek některých kvantových algoritmů je založen na pravděpodobnosti, kterou definují použité kvantové operace, je třeba tyto výpočty spouštět několikrát, aby bylo možné na základě pravděpodobnostního rozdělení zpřesnit výsledky.  Ujištění, že operace vrátila správný výsledek, se označuje jako kvantové ověření a v kvantových výpočtech jde o významný problém.

## <a name="summary"></a>Souhrn

Kvantové výpočty sdílejí s těmi klasickými některé koncepty, ale přidávají několik zásadních zákrutů. Tady je pár klíčových pojmů:

- Kvantový hardware je nákladný a velmi citlivý, takže se pro psaní a testování programů používají kvantové simulátory.
- Klasické i kvantové počítače používají k přípravě výpočtů logické operace (nebo hradla).
- Kvantové výpočty vrací výsledky s určitou přiřazenou pravděpodobností.

Pokroky v kvantovém hardwaru a technikách programování se rychle vyvíjejí. Tady si můžete přečíst [pár novinek](https://phys.org/search/?search=quantum+computer&s=0).

## <a name="next-steps"></a>Další kroky

[Co je programovací jazyk Q# a sada QDK?](xref:microsoft.quantum.overview.q-sharp)
