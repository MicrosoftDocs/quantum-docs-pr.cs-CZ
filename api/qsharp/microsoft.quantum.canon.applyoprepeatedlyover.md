---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: Operace ApplyOpRepeatedlyOver
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 263eff8ec31f5ee36485eb1d2ed52bf15cef4bef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844805"
---
# <a name="applyoprepeatedlyover-operation"></a><span data-ttu-id="beb9d-102">Operace ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="beb9d-102">ApplyOpRepeatedlyOver operation</span></span>

<span data-ttu-id="beb9d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="beb9d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="beb9d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="beb9d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="beb9d-105">Aplikuje stejnou operaci op přes qubit registr několikrát.</span><span class="sxs-lookup"><span data-stu-id="beb9d-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="beb9d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="beb9d-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="beb9d-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="beb9d-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="beb9d-108">Operace, která se má v registru qubit použít několikrát</span><span class="sxs-lookup"><span data-stu-id="beb9d-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="beb9d-109">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="beb9d-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="beb9d-110">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="beb9d-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="beb9d-111">Každé pole by mělo obsahovat seznam čísla popisujících qubits, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="beb9d-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="beb9d-112">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="beb9d-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="beb9d-113">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="beb9d-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="beb9d-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="beb9d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="beb9d-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="beb9d-115">See Also</span></span>

- [<span data-ttu-id="beb9d-116">Microsoft. proApplySeriesOfOps. Canon.</span><span class="sxs-lookup"><span data-stu-id="beb9d-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)