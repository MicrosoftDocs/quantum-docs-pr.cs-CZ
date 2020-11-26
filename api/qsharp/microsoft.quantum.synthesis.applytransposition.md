---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operace ApplyTransposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203310"
---
# <a name="applytransposition-operation"></a>Operace ApplyTransposition

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Tato operace zamění amplitudu s indexem `a` s amplitudou v indexu `b` v daném stavu – vektor `register` délky $n $.  Pokud `a` je rovno `b` , nemění se stavový vektor.

## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

První index (musí být hodnota od 0 do $2 ^ n-$1)


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Druhý index (musí být hodnota od 0 do $2 ^ n-$1)


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Seznam $n $ qubits, na který se aplikuje provedení.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

