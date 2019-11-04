---
title: 'Q # – techniky – všechno dohromady | Microsoft Docs'
description: 'Metody Q # – všechny společně umísťují'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f65b3e260f98a7a90da13b62edd6cc63d200f5af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183263"
---
# <a name="putting-it-all-together-teleportation"></a>Vše dohromady: při přenosu #
Pojďme se vrátit na příklad okruhu přenosu definovaného v [okruhech](xref:microsoft.quantum.concepts.circuits). Budeme k tomu využít k ilustraci konceptů, které jsme doposud dozvěděli. Pro uživatele, kteří nejsou obeznámeni s teoretickou, je níže uveden výklad doby použitelnosti, za kterou následuje návod implementace kódu v Q #. 

## <a name="quantum-teleportation-theory"></a>Vystavení za sebou: teorie
Jednosměrné navýšení je technika pro posílání neznámého stavového stavu (to znamená "__zpráva__") z qubit v jednom umístění do qubit v jiném umístění (na tyto qubits odkazujeme jako__na this a__ __tam__). v uvedeném pořadí). Naši __zprávu__ můžeme znázornit jako vektor pomocí zápisu Dirac: 

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Stav __zprávy__ qubit není znám, protože neznáte hodnoty $ \Alpha $ a $ \beta $.

### <a name="step-1-create-an-entangled-state"></a>Krok 1: vytvoření stavu entangled
Aby bylo možné poslat __zprávu__ __pro qubit,__ je třeba, aby se entangled __s qubit.__ Toho dosáhnete použitím brány Hadamard, následovanou bránou CNOT. Pojďme se podívat na matematiku za těmito operacemi s bránou.

Zahájíme __vám qubits a__ ve stavu $ \ket{0}$. Po Entangling těchto qubits jsou ve stavu:

$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>Krok 2: odeslání zprávy
Pokud chcete poslat __zprávu__ , nejdřív použijte bránu CNOT se __zprávou__ qubit a __tady__ qubit jako vstupy ( __zpráva__ qubit je ovládací prvek a __tady__ qubit v této instanci je cílová qubit). Tento stav vstupu lze zapsat:

$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $

Rozšiřuje se na:

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $

V rámci připomenutí CNOT brána Překlopí cílovou qubit, když je ovládací prvek qubit 1. Například vstup $ \ket{000}$ nebude mít za následek změnu jako první qubit (ovládací prvek) je 0. Nicméně si povezměte případ, kde první qubit je 1 – například vstup typu $ \ket{100}$. V tomto případě je výstupem $ \ket{110}$ jako druhý qubit (cíl) převrácenou bránou CNOT.

Pojďme teď považovat výstup, jakmile se CNOT brána na náš vstup výše. Výsledek je následující:

$ $ \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

Dalším krokem k odeslání __zprávy__ je použití brány Hadamard pro qubit __zprávy__ (to je první qubit každé podmínky). 

Brána Hadamard má jako připomenutí následující:

Vstup | Výstup
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $

Pokud použijeme bránu Hadamard na první qubit každého předplatného našeho výstupu, získáme následující výsledek:

$ $ \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{ \sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $

Všimněte si, že každý výraz má $2 \frac{1}{\sqrt{2}} $ faktorů. Tyto výsledky můžeme vynásobit následujícím výsledkům:

$ $ \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $

Výraz $ \frac{1}{2}$ Factor je společný pro každý termín, takže ho teď můžeme vzít mimo hranaté závorky:

$ $ \frac{1}{2}\big [\Alpha (\ket{0} + \ket{1}) \ket{00} + \Alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $

Pak můžeme vynásobit hranaté závorky pro každý termín, který poskytuje:

$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $

### <a name="step-3-measure-the-result"></a>Krok 3: měření výsledku

V důsledku toho se __tady__ __a entangled__ všechna měření, která __zde__ ovlivní __stav.__ Pokud si vyměříme první a druhý qubit (__zpráva__ a __tady__), můžeme zjistit, v čem se __nachází stav z__ důvodu této vlastnosti entanglement. 

* Pokud budeme měřit a získat výsledek 00, nadměrná pozice se sbalí a zachová pouze ty výrazy, které jsou v souladu s tímto výsledkem. To je $ \alpha\ket{000} + \beta\ket{001}$. Dá se Refaktorovat na $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $. Proto v __případě, že__je třeba změřit první a druhý qubit jako 00, víme, že třetí qubit je ve stavu $ (\alpha\ket{0} + \beta\ket{1}) $.
* Pokud měříme a získáte výsledek 01, nadměrná pozice se sbalí a zachová jenom ty výrazy, které jsou v souladu s tímto výsledkem. To je $ \alpha\ket{011} + \beta\ket{010}$. Dá se Refaktorovat na $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $. Proto v __případě, že__je třeba změřit první a druhý qubit na hodnotu 01, víme, že třetí qubit je ve stavu \ (\alpha\ket{1} + \beta\ket{0}) $.
* Pokud provedeme měření a získáte výsledek 10, pozice se sbalí a zachová jenom ty výrazy, které jsou v souladu s tímto výsledkem. To je $ \alpha\ket{100}-\beta\ket{101}$. To lze Refaktorovat na $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $. Proto v případě, že měříme první a druhý qubit na 10, ví, že třetí qubit, je __tam__ve stavu $ (\alpha\ket{0}-\beta\ket{1}) $.
* Pokud provedeme měření a dostanete výsledek 11, pozice se sbalí a ponechává se jenom ty, které jsou v souladu s tímto výsledkem. To je $ \alpha\ket{111}-\beta\ket{110}$. To lze Refaktorovat na $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $. Proto v __případě, že__je třeba změřit první a druhý qubit na hodnotu 11, víme, že třetí qubit je ve stavu $ (\alpha\ket{1}-\beta\ket{0}) $.

### <a name="step-4-interpret-the-result"></a>Krok 4: interpretace výsledku

V rámci připomenutí byla původní __zpráva__ , kterou jsme chtěli poslat,:

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Musíme do tohoto stavu dostat __qubit,__ aby byl přijatý stav ten, který byl určen. 

* Pokud jsme zjistili a získali výsledek 00, pak je třetí qubit ve stavu $(\alpha\ket{0} + \beta\ket{1}) $. Vzhledem k tomu, že se jedná o zamýšlenou __zprávu__, není nutná žádná změna.
* Pokud jsme zjistili a získali výsledek __01, pak__je třetí qubit ve stavu $ (\alpha\ket{1} + \beta\ket{0}) $. To se liší od zamýšlené __zprávy__, ale použití nebrány nám poskytuje požadovaný stav $ (\alpha\ket{0} + \beta\ket{1}) $.
* Pokud jsme nahodnotili a získali výsledek 10, je třetí qubit ve stavu$ (\alpha\ket{0}-\beta\ket{1}) $. To se liší od zamýšlené __zprávy__, ale použití brány z nám poskytuje požadovaný stav $ (\alpha\ket{0} + \beta\ket{1}) $.
* Pokud jsme nahodnotili a získali výsledek __11, je__třetí qubit ve stavu $ (\alpha\ket{1}-\beta\ket{0}) $. To se liší od zamýšlené __zprávy__, ale použití nebrány následované bránou Z nám poskytuje požadovaný stav $ (\alpha\ket{0} + \beta\ket{1}) $.

V případě, že se jedná o míru a první qubit je 1, je použita Brána Z. Pokud budeme měřit a druhý qubit je 1, nepoužije se žádná brána.

### <a name="summary"></a>Souhrn
Níže je uvedený okruh, který je v textovém poli okruh, který implementuje přenos. Přesunutí zleva doprava můžete zobrazit:
- Krok 1: Entangling __sem__ a __tam__ , kde použijete bránu HADAMARD a bránu CNOT.
- Krok 2: odeslání __zprávy__ pomocí brány CNOT a brány Hadamard
- Krok 3: pořízení měření první a druhé qubits, __zprávy__ a __sem__
- Krok 4: použití brány, která není typu hradlo nebo Z, v závislosti na výsledku měření v kroku 3.

![' Teleport (MSG: qubit; zde: qubit): jednotka '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Vystavení za sebou: kód

Náš okruh máme pro naši službu pro vystavování.

![' Teleport (MSG: qubit; zde: qubit): jednotka '](~/media/teleportation.svg)

Nyní můžeme přeložit každý z kroků v tomto okruhu do Q #.

### <a name="step-0-definition"></a>Krok 0: definice
Když provedeme vystavování, musíme nám sdělit __zprávu__ , kterou chceme odeslat, a tam, kde si ji přejeme poslat (__tam__). Z tohoto důvodu Začínáme definováním nové operace teleport, která je předána dvěma qubits jako argumentům, `msg` a `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Také je potřeba přidělit qubit `here`, které máme `using` blok:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Krok 1: vytvoření stavu entangled
Pak můžeme vytvořit pár entangled mezi `here` a `there` pomocí operací @"microsoft.quantum.primitive.h" a @"microsoft.quantum.primitive.cnot":

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Krok 2: odeslání zprávy
Pak použijeme další brány $ \operatorname{CNOT} $ a $H $ k přesunutí našeho qubitu zpráv:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Krok 3 & 4: měření a interpretace výsledku
Nakonec používáme @"microsoft.quantum.primitive.m" k provádění měření a k provedení potřebných operací brány k získání požadovaného stavu, jak je označený `if` příkazy:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Tím se dokončí definice našeho operátoru přenosu, takže můžeme navrátit `here`, ukončit text a ukončit operaci.

```qsharp
    }
}
```
