---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operace ApplyToEach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217862"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="8019e-102">Operace ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="8019e-102">ApplyToEach operation</span></span>

<span data-ttu-id="8019e-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8019e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8019e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8019e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8019e-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="8019e-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8019e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8019e-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="8019e-107">singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8019e-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8019e-108">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="8019e-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="8019e-109">registr: t []</span><span class="sxs-lookup"><span data-stu-id="8019e-109">register : 'T[]</span></span>

<span data-ttu-id="8019e-110">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="8019e-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8019e-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8019e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8019e-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8019e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8019e-113">'S</span><span class="sxs-lookup"><span data-stu-id="8019e-113">'T</span></span>

<span data-ttu-id="8019e-114">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="8019e-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="8019e-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="8019e-115">See Also</span></span>

- [<span data-ttu-id="8019e-116">Microsoft. proApplyToEachC. Canon.</span><span class="sxs-lookup"><span data-stu-id="8019e-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="8019e-117">Microsoft. proApplyToEachA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8019e-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="8019e-118">Microsoft. proApplyToEachCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8019e-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)