---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Operace ApplyToEachIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 746bc19f7a137ef476a25abdabc4737ed6727ff2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217607"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="dc35b-102">Operace ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="dc35b-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="dc35b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc35b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc35b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc35b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc35b-105">Aplikuje jednu operaci qubit na každý indexovaný element v registru.</span><span class="sxs-lookup"><span data-stu-id="dc35b-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="dc35b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="dc35b-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="dc35b-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc35b-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="dc35b-108">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="dc35b-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="dc35b-109">registr: t []</span><span class="sxs-lookup"><span data-stu-id="dc35b-109">register : 'T[]</span></span>

<span data-ttu-id="dc35b-110">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="dc35b-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc35b-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc35b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dc35b-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="dc35b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc35b-113">'S</span><span class="sxs-lookup"><span data-stu-id="dc35b-113">'T</span></span>

<span data-ttu-id="dc35b-114">Cíl, na kterém každá operace funguje.</span><span class="sxs-lookup"><span data-stu-id="dc35b-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc35b-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="dc35b-115">See Also</span></span>

- [<span data-ttu-id="dc35b-116">Microsoft. proApplyToEach. Canon.</span><span class="sxs-lookup"><span data-stu-id="dc35b-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="dc35b-117">Microsoft. proApplyToEachIndexA. Canon.</span><span class="sxs-lookup"><span data-stu-id="dc35b-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="dc35b-118">Microsoft. proApplyToEachIndexC. Canon.</span><span class="sxs-lookup"><span data-stu-id="dc35b-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="dc35b-119">Microsoft. proApplyToEachIndexCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="dc35b-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)