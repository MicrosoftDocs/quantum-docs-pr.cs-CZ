---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704185"
---
# <a name="embedpauli-function"></a><span data-ttu-id="39d6f-102">EmbedPauli – funkce</span><span class="sxs-lookup"><span data-stu-id="39d6f-102">EmbedPauli function</span></span>

<span data-ttu-id="39d6f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39d6f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39d6f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39d6f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39d6f-105">Po předaném operátoru qubit Pauli a indexu qubit vrátí operátor multi-qubit Pauli se zadaným operátorem s jedním qubit v tomto indexu a `PauliI` na všech ostatních indexech.</span><span class="sxs-lookup"><span data-stu-id="39d6f-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="39d6f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="39d6f-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="39d6f-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="39d6f-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="39d6f-108">Qubit Pauli operátor, který se umístí do daného umístění.</span><span class="sxs-lookup"><span data-stu-id="39d6f-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="39d6f-109">Umístění: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39d6f-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39d6f-110">Index, který `output[location] == pauli` , kde `output` je výstupem této funkce.</span><span class="sxs-lookup"><span data-stu-id="39d6f-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="39d6f-111">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39d6f-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39d6f-112">Délka pole, které se má vrátit</span><span class="sxs-lookup"><span data-stu-id="39d6f-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="39d6f-113">Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="39d6f-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

