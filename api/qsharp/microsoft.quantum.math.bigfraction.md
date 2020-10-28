---
uid: Microsoft.Quantum.Math.BigFraction
title: Uživatelem definovaný typ BigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708313"
---
# <a name="bigfraction-user-defined-type"></a>Uživatelem definovaný typ BigFraction

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček [](https://nuget.org/packages/)


Představuje racionální číslo formuláře `p/q` . Celé číslo `p` je první prvek řazené kolekce členů a `q` je druhým prvkem řazené kolekce členů.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="numerator--bigint"></a>Čitatel: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Čitatel zlomku
### <a name="denominator--bigint"></a>Jmenovatel: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Jmenovatel zlomku/