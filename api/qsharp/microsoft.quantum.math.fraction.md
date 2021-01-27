---
uid: Microsoft.Quantum.Math.Fraction
title: Typ zlomku uživatelsky definovaného typu
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857521"
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