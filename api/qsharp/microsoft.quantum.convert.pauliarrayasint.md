---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832708"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="eb800-102">PauliArrayAsInt – funkce</span><span class="sxs-lookup"><span data-stu-id="eb800-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="eb800-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="eb800-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="eb800-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="eb800-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="eb800-105">Zakóduje qubit Pauli operátor reprezentovaný jako pole operátorů s jedním qubit Pauli do celého čísla.</span><span class="sxs-lookup"><span data-stu-id="eb800-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="eb800-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="eb800-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="eb800-107">Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="eb800-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="eb800-108">Pole s maximálně 31 qubit operátory Pauli.</span><span class="sxs-lookup"><span data-stu-id="eb800-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="eb800-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb800-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb800-110">Jedinečné identifikační číslo `paulis` , jak je popsáno níže.</span><span class="sxs-lookup"><span data-stu-id="eb800-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="eb800-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="eb800-111">Remarks</span></span>

<span data-ttu-id="eb800-112">Každý operátor Pauli se dá kódovat pomocí dvou bitů: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="eb800-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="eb800-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="eb800-113">\end{align} $$</span></span>

<span data-ttu-id="eb800-114">V případě pole operátorů Pauli `[P0, ..., Pn]` vrátí tato funkce celé číslo se binárním rozšířením vytvořeným zřetězením mapování každého operátoru Pauli v pořadí big endian `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="eb800-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>