---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Operace ApplyToEachIndexA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704952"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="0dc35-102">Operace ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="0dc35-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="0dc35-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0dc35-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0dc35-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0dc35-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0dc35-105">Aplikuje jednu operaci qubit na každý indexovaný element v registru.</span><span class="sxs-lookup"><span data-stu-id="0dc35-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="0dc35-106">Modifikátor `A` označuje, že operace s jedním qubit je sousední.</span><span class="sxs-lookup"><span data-stu-id="0dc35-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0dc35-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="0dc35-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj"></a><span data-ttu-id="0dc35-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ.</span><span class="sxs-lookup"><span data-stu-id="0dc35-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0dc35-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="0dc35-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="0dc35-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="0dc35-110">register : 'T[]</span></span>

<span data-ttu-id="0dc35-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="0dc35-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0dc35-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0dc35-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0dc35-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0dc35-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0dc35-114">'S</span><span class="sxs-lookup"><span data-stu-id="0dc35-114">'T</span></span>

<span data-ttu-id="0dc35-115">Cíl, na kterém každá operace funguje.</span><span class="sxs-lookup"><span data-stu-id="0dc35-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dc35-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="0dc35-116">See Also</span></span>

- [<span data-ttu-id="0dc35-117">Microsoft. proApplyToEachIndex. Canon.</span><span class="sxs-lookup"><span data-stu-id="0dc35-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)