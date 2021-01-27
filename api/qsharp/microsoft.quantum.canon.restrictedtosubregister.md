---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: c5a6bbe16d2f6a317f6ed6f258077095465995f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840234"
---
# <a name="restrictedtosubregister-function"></a>RestrictedToSubregister – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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