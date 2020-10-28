---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: Operace ApplyOpRepeatedlyOverCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 970acfbc63bc95542827988c5c81387e8812f289
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705113"
---
# <a name="applyoprepeatedlyoverca-operation"></a><span data-ttu-id="20202-102">Operace ApplyOpRepeatedlyOverCA</span><span class="sxs-lookup"><span data-stu-id="20202-102">ApplyOpRepeatedlyOverCA operation</span></span>

<span data-ttu-id="20202-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20202-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20202-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20202-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20202-105">Aplikuje stejnou operaci op přes qubit registr několikrát.</span><span class="sxs-lookup"><span data-stu-id="20202-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="20202-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="20202-106">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="20202-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="20202-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="20202-108">Operace, která se má v registru qubit použít několikrát</span><span class="sxs-lookup"><span data-stu-id="20202-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="20202-109">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="20202-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="20202-110">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="20202-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="20202-111">Každé pole by mělo obsahovat seznam čísla popisujících qubits, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="20202-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="20202-112">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="20202-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="20202-113">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="20202-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20202-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20202-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="20202-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="20202-115">See Also</span></span>

- [<span data-ttu-id="20202-116">Microsoft. proApplySeriesOfOps. Canon.</span><span class="sxs-lookup"><span data-stu-id="20202-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)