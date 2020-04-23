---
title: Q# techniky - Uvedení to všechno dohromady
description: Projděte si základní q# program, který demonstruje kvantovou teleportaci.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030561"
---
# <a name="putting-it-all-together-teleportation"></a>Uvedení to všechno dohromady: Teleportace #
Vraťme se k příkladu teleportačního obvodu definovaného v [kvantových obvodech](xref:microsoft.quantum.concepts.circuits). Použijeme to k ilustraci konceptů, které jsme se zatím naučili. Vysvětlení kvantové teleportace je k dispozici níže pro ty, kteří nejsou obeznámeni s teorií, následuje návod implementace kódu v Q#. 

## <a name="quantum-teleportation-theory"></a>Kvantová teleportace: Teorie
Kvantová teleportace je technika pro odesílání neznámého kvantového stavu (který budeme označovat jako '__zpráva__') z qubit u jednoho místa na qubit na jiném místě (budeme odkazovat na tyto qubity jako '__zde__' a '__tam__', resp. Můžeme reprezentovat naše __poselství__ jako vektor pomocí Dirac notace: 

$$ \ket{\psi} = \alfa\ket{0} +{1} \beta\ket $$

Stav __zprávy__ qubit je neznámý pro nás, protože nevíme hodnoty $\alpha$ a $\beta$.

### <a name="step-1-create-an-entangled-state"></a>Krok 1: Vytvoření zamotaný stav
Aby bylo možné poslat __zprávu,__ musíme pro qubit __zde__ být zapletený s qubit __tam__. Toho je dosaženo použitím hadamardské brány, následovanou bránou CNOT. Podívejme se na matematiku za těmito operacemi brány.

Začneme s qubity __tu__ a __tam__ jak ve{0}stavu $\ket $. Po zamotání těchto qubitů jsou ve stavu:

$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$

### <a name="step-2-send-the-message"></a>Krok 2: Odeslání zprávy
Chcete-li poslat __zprávu__ jsme nejprve použít Brána CNOT se __zprávou__ qubit a __zde__ qubit jako vstupy __(zpráva__ qubit je ovládací prvek a __zde__ qubit je cíl qubit, v tomto případě). Tento vstupní stav lze zapsat:

$${0} \ket{\psi}\ket{\phi^+} = (\alpha\ket +{1}\beta\ket{1})(\frac {\sqrt{2}}(\ket{00} + \ket{11})) $$

Tím se zvětšujete na:

$$ \ket{\psi}\ket{\phi^+} ={2}\frac{\alpha}{\sqrt{000} }\ket +{2}\frac{\alpha}{\sqrt{011} {2}{100} {2}{111} }\ket + \frac{\beta}{\sqrt }\ket }\

Připomínáme, že brána CNOT převrátí cílový qubit, když je kontrolní qubit 1. Takže například vstup $\ket{000}$ bude mít za následek žádnou změnu jako první qubit (ovládací prvek) je 0. Vezměte však případ, kdy první qubit je 1 - například vstup $\ket{100}$. V tomto případě je výstup $\ket{110}$ jako druhý qubit (cíl) je převrácený bránou CNOT.

Podívejme se nyní na náš výstup, jakmile brána CNOT jednala na našem vstupu výše. Výsledkem je:

{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{011} {2}{110} {2}{101} {2}}\ket + \frac{\beta}{\sqrt }\ket + \frac{\beta}{\sqrt }\ket $$

Dalším krokem k odeslání __zprávy__ je použít hadamard bránu na __zprávu__ qubit (to je první qubit každého termínu). 

Připomínáme, že hadamardova brána dělá následující:

Vstup | Výstup
---------------------------| ---------------------------------------------------------------
$\ket{0}$  | $\frac{1}{\sqrt{2}}(\ket{0} +{1}\ket )$
$\ket{1}$  | $\frac{1}{\sqrt{2}}(\ket{0} -{1}\ket )$

Pokud použijeme hadamardovou bránu na první qubit každého termínu našeho výstupu výše, získáme následující výsledek:

$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}}(\ket{1}{00} {2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {1}{01} {0} + \ket))\ket + \frac{\alpha}{\sqrt }(\frac {\sqrt }(\ket + \ket))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket))\ket $$

Všimněte si, že každý{1}termín má dva{2}faktory $\frac {\sqrt }$. Můžeme je znásobit a dát takto:

$$ \frac{\alpha}{2}(\ket{0} +{1}\ket{00} )\ket +{2}\frac{\alpha} (\ket{0} + \ket{1}{11} )\ket + \frac{\beta}{2}(\ket{0} - \ket{0} {1}{01} {1})\ket )\ket{10} +\beta}{2}

$\frac{1}{2}$ faktor je společný pro každý termín, takže nyní můžeme vzít mimo závorky:

{1}{2}$$ \frac \big[\alpha(\ket{0} +{1}\ket{00} )\ket +{0} \alpha(\ket + \ket{1})\ket + \ket{11} + \ket - \ket{0} )\ket )\ket )\ket{1}{10} {0} {1}{01})\ket

Pak můžeme vynásobit závorky pro každý termín dávat:

{1}{2}$$ \frac \big[\alpha\ket{000} + \alpha\ket{100} +{011} \alpha\ket{111} + \alpha\ket{010} + \beta\ket -{001} \beta\ket{101}{110} + \beta\ket - \beta\ket \big] $$

### <a name="step-3-measure-the-result"></a>Krok 3: Měření výsledku

Vzhledem k tomu, __tu__ a __tam__ je zapletený, jakékoli měření na __zde__ bude mít vliv na stav __tam__. Pokud změříme první a druhý qubit (__zpráva__ a __zde__), můžeme se dozvědět, v jakém __stavu__ je, kvůli této vlastnosti zapletení. 

* Pokud změříme a získáme výsledek 00, superpozice se zhroutí a ponecháme pouze podmínky, které jsou v souladu s tímto výsledkem. To je $\alpha\ket{000} +\beta\ket{001}$. To může být refaktorováno{00}na $\ket{0} (\alpha\ket +\beta\ket{1})$. Proto pokud měříme první a druhý qubit být 00, víme, že třetí qubit, __tam__,{0} je ve stavu{1}$(\alpha\ket +\beta\ket )$.
* Pokud změříme a získáme výsledek 01, superpozice se zhroutí a ponecháme pouze podmínky, které jsou v souladu s tímto výsledkem. To je $\alpha\ket{011} +\beta\ket{010}$. To může být refaktorováno{01}na $\ket{1} (\alpha\ket +\beta\ket{0})$. Proto pokud měříme první a druhý qubit být 01, víme, že třetí qubit, __tam__,{1} je ve stavu{0}$(\alpha\ket +\beta\ket )$.
* Pokud změříme a získáme výsledek 10, superpozice se zhroutí a ponecháme pouze podmínky, které jsou v souladu s tímto výsledkem. To je $\alpha\ket{100} -\beta\ket{101}$. To může být refaktorováno{10}na $\ket{0} (\alpha\ket -\beta\ket{1})$. Proto pokud měříme první a druhý qubit na 10, víme, že třetí qubit, __tam__,{0} je ve stavu{1}$(\alpha\ket -\beta\ket )$.
* Pokud změříme a získáme výsledek 11, superpozice se zhroutí a ponecháme pouze podmínky, které jsou v souladu s tímto výsledkem. To je $\alpha\ket{111} -\beta\ket{110}$. To může být refaktorováno{11}na $\ket{1} (\alpha\ket -\beta\ket{0})$. Proto pokud měříme první a druhý qubit na 11, víme, že třetí qubit, __tam__,{1} je ve stavu{0}$(\alpha\ket -\beta\ket )$.

### <a name="step-4-interpret-the-result"></a>Krok 4: Interpretace výsledku

Připomínáme, že původní __zpráva,__ kterou jsme chtěli poslat, byla:

$$ \ket{\psi} = \alfa\ket{0} +{1} \beta\ket $$

Musíme se __dostat tam__ qubit do tohoto stavu, takže přijatý stav je ten, který byl určen. 

* Pokud jsme změřili a dostali výsledek 00, pak třetí qubit, __tam__,{0} je ve stavu{1}$(\alpha\ket +\beta\ket )$. Vzhledem k tomu, že se jedná o zamýšlenou __zprávu__, není nutná žádná změna.
* Pokud jsme změřili a dostali výsledek 01, pak třetí qubit, __tam__,{1} je ve stavu{0}$(\alpha\ket +\beta\ket )$. To se liší od zamýšlené __zprávy__, ale použití NOT gate nám dává{0} požadovaný stav $(\alpha\ket +\beta\ket{1})$.
* Pokud jsme změřili a dostali výsledek 10, pak třetí qubit, __tam__,{0} je ve stavu{1}$(\alpha\ket -\beta\ket )$. To se liší od zamýšlené __zprávy__, ale použití brány Z nám dává{0} požadovaný stav $(\alpha\ket +\beta\ket{1})$.
* Pokud jsme změřili a dostali výsledek 11, pak třetí qubit, __tam__,{1} je ve stavu{0}$(\alpha\ket -\beta\ket )$. To se liší od zamýšlené __zprávy__, ale použití not brány následované bránou Z{0} nám dává požadovaný{1}stav $(\alpha\ket +\beta\ket )$.

Abychom to shrnuli, pokud měříme a první qubit je 1, použije se brána Z. Pokud měříme a druhý qubit je 1, použije se brána NOT.

### <a name="summary"></a>Souhrn
Níže je uveden kvantový obvod, který implementuje teleportaci. Pohybující se zleva doprava můžete vidět:
- Krok 1: Zamotání __tu__ a __tam__ použitím Hadamard brány a CNOT brány.
- Krok 2: Odeslání __zprávy__ pomocí brány CNOT a brány Hadamard.
- Krok 3: Měření prvního a druhého qubits, __zprávy__ a __zde__.
- Krok 4: Použití brány NOT nebo brány Z, v závislosti na výsledku měření v kroku 3.

!["Teleport(msg : Qubit, tam : Qubit) : Jednotka"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Kvantová teleportace: Kód

Máme náš obvod pro kvantovou teleportaci:

!["Teleport(msg : Qubit, tam : Qubit) : Jednotka"](~/media/teleportation.svg)

Nyní můžeme přeložit každý z kroků v tomto kvantovém obvodu do Q#.

### <a name="step-0-definition"></a>Krok 0: Definice
Když provádíme teleportaci, musíme znát __zprávu,__ kterou chceme poslat, a kam ji chceme poslat __(tam).__ Z tohoto důvodu začneme definováním nové operace Teleport, která je dána `msg` `there`dva qubity jako argumenty a :

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Musíme také přidělit `here` qubit, kterého `using` dosáhneme s blokem:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Krok 1: Vytvoření zamotaný stav
Pak můžeme vytvořit zamotaný `there` pár @"microsoft.quantum.intrinsic.h" mezi @"microsoft.quantum.intrinsic.cnot" `here` a pomocí a operace:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Krok 2: Odeslání zprávy
Potom použijeme další brány $\operatorname{CNOT}$ a $H$ k přesunutí naší zprávy qubit:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Krok 3 & 4: Měření a interpretace výsledku
Nakonec používáme @"microsoft.quantum.intrinsic.m" k provedení měření a provedení nezbytných operací brány, abychom `if` získali požadovaný stav, jak je uvedeno v příkazech:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>Krok 5: Restartování registru qubit

Na konci každé operace Q# musíme nechat qubits ve stavu{0}$\ket $. Můžeme použít @"microsoft.quantum.intrinsic.reset" k restartování všech qubitů do nulového stavu a tím dokončíme naši operaci.

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


