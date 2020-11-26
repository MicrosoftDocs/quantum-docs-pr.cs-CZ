---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operace ApplyToEachC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217777"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="ccf84-102">Operace ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="ccf84-102">ApplyToEachC operation</span></span>

<span data-ttu-id="ccf84-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ccf84-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ccf84-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ccf84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ccf84-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="ccf84-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="ccf84-106">Modifikátor `C` označuje, že operace s jedním qubit je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="ccf84-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="ccf84-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="ccf84-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="ccf84-108">singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="ccf84-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ccf84-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="ccf84-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ccf84-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="ccf84-110">register : 'T[]</span></span>

<span data-ttu-id="ccf84-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="ccf84-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ccf84-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ccf84-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ccf84-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ccf84-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ccf84-114">'S</span><span class="sxs-lookup"><span data-stu-id="ccf84-114">'T</span></span>

<span data-ttu-id="ccf84-115">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="ccf84-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccf84-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="ccf84-116">See Also</span></span>

- [<span data-ttu-id="ccf84-117">Microsoft. proApplyToEach. Canon.</span><span class="sxs-lookup"><span data-stu-id="ccf84-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)