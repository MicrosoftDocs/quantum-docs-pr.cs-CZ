---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operace ApplyToEachIndexCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704937"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="ff585-102">Operace ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="ff585-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="ff585-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ff585-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ff585-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff585-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff585-105">Aplikuje jednu operaci qubit na každý indexovaný element v registru.</span><span class="sxs-lookup"><span data-stu-id="ff585-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="ff585-106">Modifikátor `CA` označuje, že operace s jedním qubit je sousední a ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="ff585-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ff585-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="ff585-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="ff585-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ff585-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ff585-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="ff585-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ff585-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="ff585-110">register : 'T[]</span></span>

<span data-ttu-id="ff585-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="ff585-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff585-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff585-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ff585-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ff585-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ff585-114">'S</span><span class="sxs-lookup"><span data-stu-id="ff585-114">'T</span></span>

<span data-ttu-id="ff585-115">Cíl, na kterém každá operace funguje.</span><span class="sxs-lookup"><span data-stu-id="ff585-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff585-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="ff585-116">See Also</span></span>

- [<span data-ttu-id="ff585-117">Microsoft. proApplyToEachIndex. Canon.</span><span class="sxs-lookup"><span data-stu-id="ff585-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)