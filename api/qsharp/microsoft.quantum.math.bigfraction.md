---
uid: Microsoft.Quantum.Math.BigFraction
title: Uživatelem definovaný typ BigFraction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846905"
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