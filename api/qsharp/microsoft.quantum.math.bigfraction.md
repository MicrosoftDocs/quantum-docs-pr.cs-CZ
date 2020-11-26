---
uid: Microsoft.Quantum.Math.BigFraction
title: Uživatelem definovaný typ BigFraction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211079"
---
# <a name="bigfraction-user-defined-type"></a>Uživatelem definovaný typ BigFraction

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje racionální číslo formuláře `p/q` . Celé číslo `p` je první prvek řazené kolekce členů a `q` je druhým prvkem řazené kolekce členů.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="numerator--bigint"></a>Čitatel: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Čitatel zlomku
### <a name="denominator--bigint"></a>Jmenovatel: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Jmenovatel zlomku/