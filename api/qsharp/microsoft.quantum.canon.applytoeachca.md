---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Operace ApplyToEachCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704960"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="b50ec-102">Operace ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="b50ec-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="b50ec-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b50ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b50ec-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b50ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b50ec-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="b50ec-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="b50ec-106">Modifikátor `CA` označuje, že operace s jedním qubit je ovladatelné a přiléhající.</span><span class="sxs-lookup"><span data-stu-id="b50ec-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b50ec-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="b50ec-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="b50ec-108">singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="b50ec-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b50ec-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="b50ec-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="b50ec-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="b50ec-110">register : 'T[]</span></span>

<span data-ttu-id="b50ec-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="b50ec-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b50ec-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b50ec-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b50ec-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b50ec-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b50ec-114">'S</span><span class="sxs-lookup"><span data-stu-id="b50ec-114">'T</span></span>

<span data-ttu-id="b50ec-115">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="b50ec-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="b50ec-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="b50ec-116">See Also</span></span>

- [<span data-ttu-id="b50ec-117">Microsoft. proApplyToEach. Canon.</span><span class="sxs-lookup"><span data-stu-id="b50ec-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)