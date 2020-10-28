---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698885"
---
# <a name="restrictedtosubregister-function"></a>RestrictedToSubregister – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Omezí operaci na pole indexů registru, tj. na podregistr.

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má omezit na podregistr


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole indexů, které určuje, které qubits operace budou omezeny.



## <a name="output--qubit--unit"></a>Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 



## <a name="see-also"></a>Viz také

- [Microsoft. proRestrictedToSubregisterA. Canon.](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [Microsoft. proRestrictedToSubregisterC. Canon.](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [Microsoft. proRestrictedToSubregisterCA. Canon.](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)