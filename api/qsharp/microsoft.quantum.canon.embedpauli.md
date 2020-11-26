---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207033"
---
# <a name="embedpauli-function"></a>EmbedPauli – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Po předaném operátoru qubit Pauli a indexu qubit vrátí operátor multi-qubit Pauli se zadaným operátorem s jedním qubit v tomto indexu a `PauliI` na všech ostatních indexech.

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>Vstup

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Qubit Pauli operátor, který se umístí do daného umístění.


### <a name="location--int"></a>Umístění: [int](xref:microsoft.quantum.lang-ref.int)

Index, který `output[location] == pauli` , kde `output` je výstupem této funkce.


### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Délka pole, které se má vrátit



## <a name="output--pauli"></a>Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

