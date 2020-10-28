---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operace ApplyToEachC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704968"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="a41fb-102">Operace ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="a41fb-102">ApplyToEachC operation</span></span>

<span data-ttu-id="a41fb-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a41fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a41fb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a41fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a41fb-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="a41fb-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="a41fb-106">Modifikátor `C` označuje, že operace s jedním qubit je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="a41fb-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a41fb-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="a41fb-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="a41fb-108">singleElementOperation: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="a41fb-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a41fb-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="a41fb-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="a41fb-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="a41fb-110">register : 'T[]</span></span>

<span data-ttu-id="a41fb-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="a41fb-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a41fb-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a41fb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a41fb-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a41fb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a41fb-114">'S</span><span class="sxs-lookup"><span data-stu-id="a41fb-114">'T</span></span>

<span data-ttu-id="a41fb-115">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="a41fb-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="a41fb-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="a41fb-116">See Also</span></span>

- [<span data-ttu-id="a41fb-117">Microsoft. proApplyToEach. Canon.</span><span class="sxs-lookup"><span data-stu-id="a41fb-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)