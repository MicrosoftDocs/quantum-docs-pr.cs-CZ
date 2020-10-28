---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Operace ApplyOpRepeatedlyOverC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: effd61e6c012dcf81a83383c3fd43cf745d18117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705120"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="77f2c-102">Operace ApplyOpRepeatedlyOverC</span><span class="sxs-lookup"><span data-stu-id="77f2c-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="77f2c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="77f2c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="77f2c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77f2c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="77f2c-105">Aplikuje stejnou operaci op přes qubit registr několikrát.</span><span class="sxs-lookup"><span data-stu-id="77f2c-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="77f2c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="77f2c-106">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="77f2c-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = seznam Ctl pro> [jednotku](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77f2c-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="77f2c-108">Operace, která se má v registru qubit použít několikrát</span><span class="sxs-lookup"><span data-stu-id="77f2c-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="77f2c-109">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="77f2c-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="77f2c-110">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="77f2c-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="77f2c-111">Každé pole by mělo obsahovat seznam čísla popisujících qubits, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="77f2c-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="77f2c-112">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="77f2c-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="77f2c-113">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="77f2c-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="77f2c-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77f2c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="77f2c-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="77f2c-115">See Also</span></span>

- [<span data-ttu-id="77f2c-116">Microsoft. proApplySeriesOfOps. Canon.</span><span class="sxs-lookup"><span data-stu-id="77f2c-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)