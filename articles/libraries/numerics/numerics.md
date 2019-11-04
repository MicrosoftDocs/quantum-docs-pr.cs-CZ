---
title: Použití knihovny numerických knihoven | Microsoft Docs
description: Použití knihovny numerických knihoven
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 332781a4356015461426ee7640fd931a41450367
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184606"
---
# <a name="using-the-numerics-library"></a>Použití knihovny numerických knihoven

## <a name="overview"></a>Přehled

Knihovna numerických typů se skládá ze tří součástí

1. **Základní celočíselná aritmetická operace** s přidanými celočíselnými a komparátorů
1. **Celočíselná funkce vysoké úrovně** , která je postavená na základních funkcích. zahrnuje násobení, dělení, inverze atd.  pro podepsaná a nepodepsaná celá čísla.
1. **Aritmetické funkce s pevnou desetinnou** čárkou s inicializací s pevnou desetinnou čárkou, sčítání, násobení, recipročního, polynomických vyhodnocení a měření.

Všechny tyto součásti jsou k dispozici pomocí jednoho příkazu `open`:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Druhy

Knihovna numerických hodnot podporuje následující typy.

1. **`LittleEndian`** : `qArr : Qubit[]` pole qubit, které představuje celé číslo, kde `qArr[0]` označuje nejméně významný bit.
1. **`SignedLittleEndian`** : totéž jako `LittleEndian` s tím rozdílem, že představuje celé číslo se znaménkem uložené ve dvou doplňkech.
1. **`FixedPoint`** : představuje reálné číslo sestávající z `qArr2 : Qubit[]` pole qubit a umístění binárního bodu `pos`, které počítá počet binárních číslic nalevo od binárního bodu. `qArr2` je uložen stejným způsobem jako `SignedLittleEndian`.

## <a name="operations"></a>Operations

Pro každý ze tří typů uvedených výše je k dispozici celá řada operací:

1. **`LittleEndian`**
    - Sčítání
    - Porovnání
    - Násobení
    - Umocnění
    - Dělení (se zbytkem)

1. **`SignedLittleEndian`**
    - Sčítání
    - Porovnání
    - Doplněk modulo 2 pro inverze
    - Násobení
    - Umocnění

1. **`FixedPoint`**
    - Příprava/inicializace na klasické hodnoty
    - Sčítání (klasická konstanta nebo jiná pevná desetinná čárka)
    - Porovnání
    - Násobení
    - Umocnění
    - Polynomické hodnocení pomocí specializace pro sudé a liché funkce
    - Oboustranný (1/x)
    - Měření (klasická dvojitá přesnost)

Další informace a podrobnou dokumentaci ke každé z těchto operací najdete v tématu Referenční dokumentace knihovny Q # na adrese [docs.Microsoft.com](https://docs.microsoft.com/en-us/quantum) .

## <a name="sample-integer-addition"></a>Ukázka: sčítání celých čísel

Jako základní příklad zvažte operaci $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ to znamená, že operace, která přebírá n-qubit Integer $x $ a n-nebo (n + 1)-qubit zaregistrovat $y $ jako vstup, přičemž ten, který se mapuje na součet $ (x + y) $. Všimněte si, že součet je vypočítán modulo $2 ^ n $, pokud je $y $ Uloženo v registru $n $-bit.

Pomocí vývojové sady pro práci s více operačními systémem můžete tuto operaci použít takto:
```qsharp
operation MyAdditionTest (xInt : Int, yInt : Int, n : Int) : Unit
{
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xInt, x); // initialize values
        ApplyXorInPlace(yInt, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Ukázka: vyhodnocení hladkých funkcí

Aby bylo možné vyhodnotit plynulé funkce, jako je $ \sin (x) $, na počítači s procesorem, kde $x $ je `FixedPoint` `Evaluate[Even/Odd]PolynomialFxP``EvaluatePolynomialFxP` číslo?

První `EvaluatePolynomialFxP`umožňuje vyhodnotit polynomu ve tvaru $ $ P (x) = A_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, kde $d $ označuje *stupeň*. To provedete tak, že všechno, co je potřeba, jsou polynomické koeficienty `[a_0,..., a_d]` (typu `Double[]`), vstupní `x : FixedPoint` a výstupní `y : FixedPoint` (zpočátku nula):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
Výsledek, $P (x) = 1 + 2x $, bude uložen v `yFxP`.

Druhý, `EvaluateEvenPolynomialFxP`a třetí `EvaluateOddPolynomialFxP`, jsou specializace pro případy, které jsou i pro jiné funkce, v uvedeném pořadí. To znamená, že pro sudé/liché funkce $f (x) $ a $ $ P_ {sudý} (x) = A_0 + A_1 x ^ 2 + A_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ je přibližná, že $P _ {sudý} (x) $ nebo $P _ {liché} (x): = x\cdot P_ {sudý} (x) $ přestup.
V Q # lze tyto dva případy zpracovat následujícím způsobem:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
který vyhodnocuje $P _ {sudý} (x) = 1 + 2x ^ 2 $ a
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
který vyhodnocuje $P _ {liché} (x) = x + 2x ^ 3 $.

## <a name="more-samples"></a>Další ukázky

Další ukázky najdete v části [hlavní úložiště ukázek](https://github.com/Microsoft/Quantum).

Začněte tím, že naklonujte úložiště a otevřete podsložku `Numerics`:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

Pak `cd` do jedné z ukázkových složek a spusťte ukázku prostřednictvím

```bash
dotnet run
```
