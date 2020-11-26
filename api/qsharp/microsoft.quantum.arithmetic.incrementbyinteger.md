---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operace IncrementByInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fa5e75e91206aa5f33233c8a54d6e9e7ac2950e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222962"
---
# <a name="incrementbyinteger-operation"></a>Operace IncrementByInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zvýší nepodepsaná bezplatných hodnot do registru pomocí klasického celého čísla pomocí otočení fáze.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Předpokládejme, že `target` kódování unsigned integer $x $ v kódování Little endian a `increment` je rovno $a $.
Tato operace pak implementuje jednotkové $ \ket{x} \mapsto \ket{x + a} $, kde sčítání se provádí modulo $2 ^ n $, kde $n = \texttt{Length (Target!)} $.

## <a name="input"></a>Vstup

### <a name="increment--int"></a>přírůstek: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo, kterým `target` se zvyšuje hodnota.


### <a name="target--littleendian"></a>cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

V případě, že dojde k zaregistrování kódování unsigned integer pomocí kódování Little endian.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

