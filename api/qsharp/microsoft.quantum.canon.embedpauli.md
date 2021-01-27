---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840538"
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



## <a name="example"></a>Příklad

Získání pole `[PauliI, PauliI, PauliX, PauliI]` :

```qsharp
EmbedPauli(PauliX, 2, 3);
```