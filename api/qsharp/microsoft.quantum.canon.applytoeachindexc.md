---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Operace ApplyToEachIndexC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850808"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="1dd07-102">Operace ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="1dd07-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="1dd07-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1dd07-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1dd07-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1dd07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1dd07-105">Aplikuje jednu operaci qubit na každý indexovaný element v registru.</span><span class="sxs-lookup"><span data-stu-id="1dd07-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="1dd07-106">Modifikátor `C` označuje, že operace s jedním qubit je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="1dd07-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="1dd07-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="1dd07-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="1dd07-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="1dd07-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1dd07-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="1dd07-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="1dd07-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="1dd07-110">register : 'T[]</span></span>

<span data-ttu-id="1dd07-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="1dd07-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1dd07-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1dd07-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1dd07-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1dd07-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1dd07-114">'S</span><span class="sxs-lookup"><span data-stu-id="1dd07-114">'T</span></span>

<span data-ttu-id="1dd07-115">Cíl, na kterém každá operace funguje.</span><span class="sxs-lookup"><span data-stu-id="1dd07-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dd07-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="1dd07-116">See Also</span></span>

- [<span data-ttu-id="1dd07-117">Microsoft. proApplyToEachIndex. Canon.</span><span class="sxs-lookup"><span data-stu-id="1dd07-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)