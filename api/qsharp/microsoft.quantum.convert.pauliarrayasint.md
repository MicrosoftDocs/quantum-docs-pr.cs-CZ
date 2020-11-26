---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224237"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zakóduje qubit Pauli operátor reprezentovaný jako pole operátorů s jedním qubit Pauli do celého čísla.

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>Vstup

### <a name="paulis--pauli"></a>Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pole s maximálně 31 qubit operátory Pauli.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Jedinečné identifikační číslo `paulis` , jak je popsáno níže.

## <a name="remarks"></a>Poznámky

Každý operátor Pauli se dá kódovat pomocí dvou bitů: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.
\end{align} $ $

V případě pole operátorů Pauli `[P0, ..., Pn]` vrátí tato funkce celé číslo se binárním rozšířením vytvořeným zřetězením mapování každého operátoru Pauli v pořadí big endian `bits(Pn) ... bits(P0)` .