---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Operace ApplyToEachIndexC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704945"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="2245c-102">Operace ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="2245c-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="2245c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2245c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2245c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2245c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2245c-105">Aplikuje jednu operaci qubit na každý indexovaný element v registru.</span><span class="sxs-lookup"><span data-stu-id="2245c-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="2245c-106">Modifikátor `C` označuje, že operace s jedním qubit je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="2245c-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2245c-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="2245c-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-ctl"></a><span data-ttu-id="2245c-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) = seznam CTL>ch [jednotek](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2245c-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="2245c-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="2245c-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="2245c-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="2245c-110">register : 'T[]</span></span>

<span data-ttu-id="2245c-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="2245c-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2245c-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2245c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2245c-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2245c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2245c-114">'S</span><span class="sxs-lookup"><span data-stu-id="2245c-114">'T</span></span>

<span data-ttu-id="2245c-115">Cíl, na kterém každá operace funguje.</span><span class="sxs-lookup"><span data-stu-id="2245c-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="2245c-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="2245c-116">See Also</span></span>

- [<span data-ttu-id="2245c-117">Microsoft. proApplyToEachIndex. Canon.</span><span class="sxs-lookup"><span data-stu-id="2245c-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)