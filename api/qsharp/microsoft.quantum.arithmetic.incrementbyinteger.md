---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operace IncrementByInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 9c7ff6947964a4dbe07106d1def9be46f631f5cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843171"
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

