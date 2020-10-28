---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Operace ApplyToEachIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704953"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="5a471-102">Operace ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="5a471-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="5a471-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5a471-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5a471-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a471-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a471-105">Aplikuje jednu operaci qubit na každý indexovaný element v registru.</span><span class="sxs-lookup"><span data-stu-id="5a471-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5a471-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5a471-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="5a471-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a471-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5a471-108">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="5a471-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="5a471-109">registr: t []</span><span class="sxs-lookup"><span data-stu-id="5a471-109">register : 'T[]</span></span>

<span data-ttu-id="5a471-110">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="5a471-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a471-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a471-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5a471-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5a471-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5a471-113">'S</span><span class="sxs-lookup"><span data-stu-id="5a471-113">'T</span></span>

<span data-ttu-id="5a471-114">Cíl, na kterém každá operace funguje.</span><span class="sxs-lookup"><span data-stu-id="5a471-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a471-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="5a471-115">See Also</span></span>

- [<span data-ttu-id="5a471-116">Microsoft. proApplyToEach. Canon.</span><span class="sxs-lookup"><span data-stu-id="5a471-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="5a471-117">Microsoft. proApplyToEachIndexA. Canon.</span><span class="sxs-lookup"><span data-stu-id="5a471-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="5a471-118">Microsoft. proApplyToEachIndexC. Canon.</span><span class="sxs-lookup"><span data-stu-id="5a471-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="5a471-119">Microsoft. proApplyToEachIndexCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="5a471-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)