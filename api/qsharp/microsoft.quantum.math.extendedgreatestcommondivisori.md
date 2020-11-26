---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195522"
---
# <a name="extendedgreatestcommondivisori-function"></a>ExtendedGreatestCommonDivisorI – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vypočítá řazenou kolekci členů $ (u, v) $, což $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, kde $ \operatorname{GCD} $ je $a $ největší společný dělitel $a $ a $b $. GCD je vždy pozitivní.

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

první číslo, které je vypočítáno jako největšího nejdelšího společného dělitele


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

druhý počet, od kterého se počítá rozšířený největší dělitel



## <a name="output--intint"></a>Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Řazená kolekce členů $ (u, v) $ s vlastností $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.

## <a name="references"></a>Reference

- Tato implementace je podle https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm