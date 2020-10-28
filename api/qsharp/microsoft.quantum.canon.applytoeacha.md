---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: Operace ApplyToEachA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704976"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="d82db-102">Operace ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="d82db-102">ApplyToEachA operation</span></span>

<span data-ttu-id="d82db-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d82db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d82db-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d82db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d82db-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="d82db-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="d82db-106">Modifikátor `A` označuje, že operace s jedním qubit je sousední.</span><span class="sxs-lookup"><span data-stu-id="d82db-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d82db-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d82db-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj"></a><span data-ttu-id="d82db-108">singleElementOperation: t [=> ADJ](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d82db-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d82db-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="d82db-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="d82db-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="d82db-110">register : 'T[]</span></span>

<span data-ttu-id="d82db-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="d82db-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d82db-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d82db-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d82db-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d82db-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d82db-114">'S</span><span class="sxs-lookup"><span data-stu-id="d82db-114">'T</span></span>

<span data-ttu-id="d82db-115">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="d82db-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="d82db-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="d82db-116">See Also</span></span>

- [<span data-ttu-id="d82db-117">Microsoft. proApplyToEach. Canon.</span><span class="sxs-lookup"><span data-stu-id="d82db-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)