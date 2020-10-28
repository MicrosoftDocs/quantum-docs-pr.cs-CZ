---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operace ApplyToEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704984"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="fafd2-102">Operace ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="fafd2-102">ApplyToEach operation</span></span>

<span data-ttu-id="fafd2-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fafd2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fafd2-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fafd2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fafd2-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="fafd2-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fafd2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fafd2-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="fafd2-107">singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fafd2-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fafd2-108">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="fafd2-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="fafd2-109">registr: t []</span><span class="sxs-lookup"><span data-stu-id="fafd2-109">register : 'T[]</span></span>

<span data-ttu-id="fafd2-110">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="fafd2-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fafd2-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fafd2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fafd2-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fafd2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fafd2-113">'S</span><span class="sxs-lookup"><span data-stu-id="fafd2-113">'T</span></span>

<span data-ttu-id="fafd2-114">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="fafd2-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="fafd2-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="fafd2-115">See Also</span></span>

- [<span data-ttu-id="fafd2-116">Microsoft. proApplyToEachC. Canon.</span><span class="sxs-lookup"><span data-stu-id="fafd2-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="fafd2-117">Microsoft. proApplyToEachA. Canon.</span><span class="sxs-lookup"><span data-stu-id="fafd2-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="fafd2-118">Microsoft. proApplyToEachCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="fafd2-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)