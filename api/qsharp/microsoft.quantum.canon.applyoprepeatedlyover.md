---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: Operace ApplyOpRepeatedlyOver
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 09f54be33a7b5c58a317a949290f5cd6d54fe841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705129"
---
# <a name="applyoprepeatedlyover-operation"></a><span data-ttu-id="60cec-102">Operace ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="60cec-102">ApplyOpRepeatedlyOver operation</span></span>

<span data-ttu-id="60cec-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="60cec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="60cec-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60cec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60cec-105">Aplikuje stejnou operaci op přes qubit registr několikrát.</span><span class="sxs-lookup"><span data-stu-id="60cec-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="60cec-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="60cec-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="60cec-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60cec-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="60cec-108">Operace, která se má v registru qubit použít několikrát</span><span class="sxs-lookup"><span data-stu-id="60cec-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="60cec-109">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="60cec-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="60cec-110">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="60cec-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="60cec-111">Každé pole by mělo obsahovat seznam čísla popisujících qubits, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="60cec-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="60cec-112">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="60cec-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="60cec-113">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="60cec-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60cec-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60cec-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="60cec-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="60cec-115">See Also</span></span>

- [<span data-ttu-id="60cec-116">Microsoft. proApplySeriesOfOps. Canon.</span><span class="sxs-lookup"><span data-stu-id="60cec-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)