---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Operace ApplyToEachC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850852"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="ce939-102">Operace ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="ce939-102">ApplyToEachC operation</span></span>

<span data-ttu-id="ce939-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce939-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce939-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce939-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce939-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="ce939-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="ce939-106">Modifikátor `C` označuje, že operace s jedním qubit je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="ce939-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="ce939-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="ce939-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="ce939-108">singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="ce939-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ce939-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="ce939-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ce939-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="ce939-110">register : 'T[]</span></span>

<span data-ttu-id="ce939-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="ce939-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce939-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce939-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ce939-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ce939-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ce939-114">'S</span><span class="sxs-lookup"><span data-stu-id="ce939-114">'T</span></span>

<span data-ttu-id="ce939-115">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="ce939-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="ce939-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="ce939-116">Example</span></span>

<span data-ttu-id="ce939-117">Připravte tři-qubit $ \ket{+} $ stav:</span><span class="sxs-lookup"><span data-stu-id="ce939-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="ce939-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="ce939-118">See Also</span></span>

- [<span data-ttu-id="ce939-119">Microsoft. proApplyToEach. Canon.</span><span class="sxs-lookup"><span data-stu-id="ce939-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)