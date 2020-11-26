---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Operace ApplyToEachIndexCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208937"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="6504e-102">Operace ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="6504e-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="6504e-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6504e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6504e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6504e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6504e-105">Aplikuje jednu operaci qubit na každý indexovaný element v registru.</span><span class="sxs-lookup"><span data-stu-id="6504e-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="6504e-106">Modifikátor `CA` označuje, že operace s jedním qubit je sousední a ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="6504e-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6504e-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="6504e-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="6504e-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="6504e-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6504e-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="6504e-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="6504e-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="6504e-110">register : 'T[]</span></span>

<span data-ttu-id="6504e-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="6504e-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6504e-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6504e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6504e-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6504e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6504e-114">'S</span><span class="sxs-lookup"><span data-stu-id="6504e-114">'T</span></span>

<span data-ttu-id="6504e-115">Cíl, na kterém každá operace funguje.</span><span class="sxs-lookup"><span data-stu-id="6504e-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="6504e-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="6504e-116">See Also</span></span>

- [<span data-ttu-id="6504e-117">Microsoft. proApplyToEachIndex. Canon.</span><span class="sxs-lookup"><span data-stu-id="6504e-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)