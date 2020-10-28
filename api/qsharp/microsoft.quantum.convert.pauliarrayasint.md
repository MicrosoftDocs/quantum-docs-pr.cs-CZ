---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698265"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="792f1-102">PauliArrayAsInt – funkce</span><span class="sxs-lookup"><span data-stu-id="792f1-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="792f1-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="792f1-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="792f1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="792f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="792f1-105">Zakóduje qubit Pauli operátor reprezentovaný jako pole operátorů s jedním qubit Pauli do celého čísla.</span><span class="sxs-lookup"><span data-stu-id="792f1-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="792f1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="792f1-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="792f1-107">Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="792f1-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="792f1-108">Pole s maximálně 31 qubit operátory Pauli.</span><span class="sxs-lookup"><span data-stu-id="792f1-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="792f1-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="792f1-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="792f1-110">Jedinečné identifikační číslo `paulis` , jak je popsáno níže.</span><span class="sxs-lookup"><span data-stu-id="792f1-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="792f1-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="792f1-111">Remarks</span></span>

<span data-ttu-id="792f1-112">Každý operátor Pauli se dá kódovat pomocí dvou bitů: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="792f1-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="792f1-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="792f1-113">\end{align} $$</span></span>

<span data-ttu-id="792f1-114">V případě pole operátorů Pauli `[P0, ..., Pn]` vrátí tato funkce celé číslo se binárním rozšířením vytvořeným zřetězením mapování každého operátoru Pauli v pořadí big endian `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="792f1-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>