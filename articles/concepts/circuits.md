---
title: Okruhy za sebou | Microsoft Docs
description: Kvantové okruhy
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: fe845aa0dde7c780ea6721dfe2559119e90b4aa5
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820789"
---
# <a name="quantum-circuits"></a>Okruhy
Vezměte v úvahu za chvilku, že se jedná o jednotnou transformaci $ \Text{CNOT} _{01}(H\otimes 1) $.
Tato sekvence brány má zásadní význam pro výpočetní výkon, protože vytváří qubit stav s maximální entangled:

$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $

Operace s touto nebo větší složitou složitostí jsou všudypřítomný s využitím algoritmů pro provozní a přístupnosti chyb, takže by měly být skvělé, že pro svou vizualizaci se používá jednoduchá metoda, která se nazývá *diagram okruhu*.
Diagram okruhu pro přípravu tohoto maximálního entangledého stavu je:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a>Konvence diagramu pro okruhy
Tento vizuál pro práci s více operačními operacemi může být mnohem snadno digestible než zapsání jeho ekvivalentní matrice, jakmile pochopíte konvence pro vyjádření okruhu.
Tyto konvence prověříme níže.

V diagramu okruhu každá plná čára znázorňuje qubit nebo více všeobecně qubit Registry.
Podle konvence je horním řádkem qubit Register $0 $ a zbytek je označený sekvenčně. Výše uvedený příklad okruhu je znázorněný na dvou qubits (nebo ekvivalentních dvou registrech, které se skládají z jednoho qubit).
Brány fungující na jednom nebo více registrech qubit jsou označeny jako pole.
Například symbol

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

je [Hadamard](xref:microsoft.quantum.intrinsic.h) brána, která funguje v registru s jedním qubit.

Vyřazení z více procesorů je seřazené v chronologickém pořadí s bránou, která je nejvíce vlevo, jako brána se jako první používá pro qubits.
Jinými slovy, pokud se dráty naformátují jako držící stav, vodiče přinášejí stav u všech bran v diagramu zleva doprava.
Řekněme, že 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

je jednotná matice $CBA $.
Násobení matice dodržuje opačnou konvenci: nejprve se použije matice nejvyšší výše. V diagramech okruhu ve službě pro vytváření koncových procesorů se ale jako první používá brána vlevo.
Tento rozdíl může v některých případech vést k nejasnostem, takže je důležité si všimnout tohoto významného rozdílu mezi lineárním zápisem algebraických a diagramy okruhu.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Vstupy a výstupy okruhů
Všechny předchozí uvedené příklady mají přesně stejný počet vodičů (qubits), jako je počet vodičů v bráně pro plnění.
Je možné, že se zpočátku jeví jako přiměřená, že okruhy by mohly mít více nebo méně výstupů, než jsou vstupy obecně.
To však není možné, protože všechny provozní operace šetří měření, jsou jednotně a tedy vratné.
Pokud neobsahují stejný počet výstupů jako vstupy, které by nebyly vratné, a proto nejsou v rozporu.
Z tohoto důvodu musí mít jakékoli pole vykreslené v diagramu okruhu přesně stejný počet vodičů, kteří ho vstupují při jeho ukončení.

Diagramy okruhu s více qubit se podobají podobným konvencím pro qubit.
Jako objasnění příkladu můžeme definovat qubit jednotkovou $B operaci $ (H S\otimes X) $ a objasnit okruh stejným způsobem jako

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

V závislosti na kontextu, ve kterém se okruh používá, můžeme také zobrazit $B $ jako akce v jednom qubit registru, nikoli 2 1-qubit Registry. Nejužitečnější vlastností takových diagramů s abstraktním okruhem je pravděpodobně to, že umožňují složitosti složitých algoritmů na vysoké úrovni, aniž by bylo nutné je kompilovat na základní brány.
To znamená, že můžete získat Intuition o toku dat pro velký algoritmus, aniž byste museli porozumět všem podrobnostem o tom, jak jednotlivé podrutiny v rámci algoritmu fungují.

## <a name="controlled-gates"></a>Řízené brány
Druhá konstrukce, která je integrovaná do qubitch okruhů, je řídicích diagramů.
Akce u jednorázového počtu jader, označených jako $ \Lambda (G) $, kde hodnota jednoho qubit řídí aplikaci $G $, se dá pochopit tak, že se podíváme na následující příklad vstupu stavu produktu $ \Lambda (G) (\Alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \Alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psí} $.
To znamená, že řízená brána se vztahuje $G $ na registr obsahující $ \psi $ if a jenom v případě, že qubit ovládacího prvku převezme hodnotu $1 $.
Obecně popisujeme tyto řízené operace v diagramech okruhů jako

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

Tady černý kroužek označuje bit, na kterém je brána řízená, a vertikální kabel označuje jednotnou, která se použije, když qubit ovládacího prvku převezme hodnotu $1 $.
Pro zvláštní případy, kdy $G = X $ a $G = Z $ zavádíme následující zápis, který popíše řízenou verzi bran (Všimněte si, že brána řízená-X je rozhraní [$CNOT $](xref:microsoft.quantum.intrinsic.cnot)):

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

Q # poskytuje metody pro automatické generování řízené verze operace, která bude ukládat programátora z nutnosti kódování těchto operací. Příklad najdete tady:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Operátor měření
Zbývající operace vizualizace v diagramech okruhů je měření.
Měření bere v qubit registraci, měří ho a výsledek vyprodukuje jako klasické informace.
Operace měření je označená symbolem měřiče a vždycky přebírá jako vstup qubit registr (označený plnou čárou) a výstupem klasických informací (označených dvojitou čárou).
Konkrétně takový okruh vypadá takto:

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
okruh měření ![](~/media/concepts_7.png)

Q # implementuje pro tento účel [operátor míry](xref:microsoft.quantum.intrinsic.measure) .
Další informace najdete v [části o měřeních](xref:microsoft.quantum.libraries.standard.prelude#measurements) .

Podobně, předaný okruh

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

poskytuje klasický monitorovanou bránu, kde $G $ se aplikuje v případě, že je pro klasický řídicí bit nastavená hodnota $1 $.

## <a name="teleportation-circuit-diagram"></a>Diagram okruhu přenosu
Pro ilustraci těchto [komponent je možná](xref:microsoft.quantum.techniques.puttingittogether) nejlepší výkon
Navýšení doby provozu je metoda pro přesouvání dat v rámci počítače s přístavou (nebo dokonce i mezi vzdálenými počítači v přístavu) pomocí entanglement a měření.
Vzhledem k tomu, že je to v podstatě schopné přesunovat stav, který je v daném qubit, je z jednoho qubit na jiný, bez ohledu na to, jaká hodnota qubit je!
To je nezbytné, aby protokol fungoval v souladu s zákony na mechanismy plnění.
Okruh pro stavovou dopravu je uveden níže. Poskytujeme také verzi okruhu s poznámkou, která ukazuje, jak číst okruh.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
