---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Operace ApplyToEachIndexA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850833"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="5ac10-102">Operace ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="5ac10-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="5ac10-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ac10-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ac10-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ac10-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ac10-105">Aplikuje jednu operaci qubit na každý indexovaný element v registru.</span><span class="sxs-lookup"><span data-stu-id="5ac10-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="5ac10-106">Modifikátor `A` označuje, že operace s jedním qubit je sousední.</span><span class="sxs-lookup"><span data-stu-id="5ac10-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5ac10-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="5ac10-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="5ac10-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="5ac10-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5ac10-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="5ac10-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="5ac10-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="5ac10-110">register : 'T[]</span></span>

<span data-ttu-id="5ac10-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="5ac10-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ac10-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ac10-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5ac10-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5ac10-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ac10-114">'S</span><span class="sxs-lookup"><span data-stu-id="5ac10-114">'T</span></span>

<span data-ttu-id="5ac10-115">Cíl, na kterém každá operace funguje.</span><span class="sxs-lookup"><span data-stu-id="5ac10-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ac10-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="5ac10-116">See Also</span></span>

- [<span data-ttu-id="5ac10-117">Microsoft. proApplyToEachIndex. Canon.</span><span class="sxs-lookup"><span data-stu-id="5ac10-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)