---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: Operace ApplyToEachA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844602"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="abc2d-102">Operace ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="abc2d-102">ApplyToEachA operation</span></span>

<span data-ttu-id="abc2d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="abc2d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="abc2d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="abc2d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="abc2d-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="abc2d-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="abc2d-106">Modifikátor `A` označuje, že operace s jedním qubit je sousední.</span><span class="sxs-lookup"><span data-stu-id="abc2d-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="abc2d-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="abc2d-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="abc2d-108">singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="abc2d-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="abc2d-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="abc2d-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="abc2d-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="abc2d-110">register : 'T[]</span></span>

<span data-ttu-id="abc2d-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="abc2d-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="abc2d-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="abc2d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="abc2d-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="abc2d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="abc2d-114">'S</span><span class="sxs-lookup"><span data-stu-id="abc2d-114">'T</span></span>

<span data-ttu-id="abc2d-115">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="abc2d-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="abc2d-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="abc2d-116">Example</span></span>

<span data-ttu-id="abc2d-117">Připravte tři-qubit $ \ket{+} $ stav:</span><span class="sxs-lookup"><span data-stu-id="abc2d-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="abc2d-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="abc2d-118">See Also</span></span>

- [<span data-ttu-id="abc2d-119">Microsoft. proApplyToEach. Canon.</span><span class="sxs-lookup"><span data-stu-id="abc2d-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)