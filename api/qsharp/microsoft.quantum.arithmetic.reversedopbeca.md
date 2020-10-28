---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: ReversedOpBECA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5617e191260903ac25effc8b922810932b7dc505
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706305"
---
# <a name="reversedopbeca-function"></a>ReversedOpBECA – funkce

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Vzhledem k operaci, která trvá vstupu big-endian, vrátí novou operaci, která bude mít vstup ze Little endian.

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="op--bigendian--unit-adj--ctl"></a>op: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace, jejíž vstup má být obrácený.



## <a name="output--littleendian--unit-adj--ctl"></a>Výstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Nová operace, která přijme svůj vstup jako registr Little endian.

## <a name="see-also"></a>Viz také

- [Microsoft. prostředníky. aritmetické. ApplyReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [Microsoft. prostředníky. aritmetické. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. prostředníky. aritmetické. ReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [Microsoft. prostředníky. aritmetické. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)