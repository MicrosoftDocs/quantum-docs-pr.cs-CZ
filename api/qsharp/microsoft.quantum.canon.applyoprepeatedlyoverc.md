---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Operace ApplyOpRepeatedlyOverC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 1cf3f32f0d25c1b4437f2bdbd93171a1a2e1e760
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844780"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="84548-102">Operace ApplyOpRepeatedlyOverC</span><span class="sxs-lookup"><span data-stu-id="84548-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="84548-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84548-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84548-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84548-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84548-105">Aplikuje stejnou operaci op přes qubit registr několikrát.</span><span class="sxs-lookup"><span data-stu-id="84548-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="84548-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="84548-106">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="84548-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="84548-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="84548-108">Operace, která se má v registru qubit použít několikrát</span><span class="sxs-lookup"><span data-stu-id="84548-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="84548-109">cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="84548-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="84548-110">Vnořená pole popisující cíle pro op.</span><span class="sxs-lookup"><span data-stu-id="84548-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="84548-111">Každé pole by mělo obsahovat seznam čísla popisujících qubits, které se mají použít.</span><span class="sxs-lookup"><span data-stu-id="84548-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="84548-112">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="84548-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="84548-113">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="84548-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84548-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84548-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="84548-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="84548-115">See Also</span></span>

- [<span data-ttu-id="84548-116">Microsoft. proApplySeriesOfOps. Canon.</span><span class="sxs-lookup"><span data-stu-id="84548-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)