---
uid: Microsoft.Quantum.Math.Fraction
title: Typ zlomku uživatelsky definovaného typu
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210671"
---
# <a name="fraction-user-defined-type"></a>Typ zlomku uživatelsky definovaného typu

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje racionální číslo formuláře `p/q` . Celé číslo `p` je první prvek řazené kolekce členů a `q` je druhým prvkem řazené kolekce členů.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="numerator--int"></a>Čitatel: [int](xref:microsoft.quantum.lang-ref.int)

Čitatel zlomku
### <a name="denominator--int"></a>Jmenovatel: [int](xref:microsoft.quantum.lang-ref.int)

Jmenovatel zlomku/