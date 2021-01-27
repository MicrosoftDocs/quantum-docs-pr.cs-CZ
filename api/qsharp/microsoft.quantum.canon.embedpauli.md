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
# <a name="embedpauli-function"></a><span data-ttu-id="a8c3c-102">EmbedPauli – funkce</span><span class="sxs-lookup"><span data-stu-id="a8c3c-102">EmbedPauli function</span></span>

<span data-ttu-id="a8c3c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8c3c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8c3c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8c3c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8c3c-105">Po předaném operátoru qubit Pauli a indexu qubit vrátí operátor multi-qubit Pauli se zadaným operátorem s jedním qubit v tomto indexu a `PauliI` na všech ostatních indexech.</span><span class="sxs-lookup"><span data-stu-id="a8c3c-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="a8c3c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a8c3c-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="a8c3c-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a8c3c-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a8c3c-108">Qubit Pauli operátor, který se umístí do daného umístění.</span><span class="sxs-lookup"><span data-stu-id="a8c3c-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="a8c3c-109">Umístění: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8c3c-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a8c3c-110">Index, který `output[location] == pauli` , kde `output` je výstupem této funkce.</span><span class="sxs-lookup"><span data-stu-id="a8c3c-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="a8c3c-111">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8c3c-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a8c3c-112">Délka pole, které se má vrátit</span><span class="sxs-lookup"><span data-stu-id="a8c3c-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="a8c3c-113">Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a8c3c-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="example"></a><span data-ttu-id="a8c3c-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="a8c3c-114">Example</span></span>

<span data-ttu-id="a8c3c-115">Získání pole `[PauliI, PauliI, PauliX, PauliI]` :</span><span class="sxs-lookup"><span data-stu-id="a8c3c-115">To obtain the array `[PauliI, PauliI, PauliX, PauliI]`:</span></span>

```qsharp
EmbedPauli(PauliX, 2, 3);
```