---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d4245437f2b71abb8bf1bbe4db43ae7d2ee23799
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845756"
---
# <a name="reversedopleca-function"></a>ReversedOpLECA – funkce

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vzhledem k operaci, která trvá vstupu Little-endian, vrátí novou operaci, která bude mít vstup big-endian.

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="op--littleendian--unit--is-adj--ctl"></a>op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL

Operace, jejíž vstup má být obrácený.



## <a name="output--bigendian--unit--is-adj--ctl"></a>Výstup: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je ADJ + CTL

Nová operace, která přijme svůj vstup jako registr big-endian.

## <a name="see-also"></a>Viz také

- [Microsoft. prostředníky. aritmetické. ApplyReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [Microsoft. prostředníky. aritmetické. ReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [Microsoft. prostředníky. aritmetické. ReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [Microsoft. prostředníky. aritmetické. ReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)