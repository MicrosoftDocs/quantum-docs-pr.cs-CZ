---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Operace ApplyToEachCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: c85b33760eba8d10d9650be2f8306e4afdd1f307
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841479"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="2b041-102">Operace ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="2b041-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="2b041-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2b041-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2b041-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b041-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b041-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="2b041-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="2b041-106">Modifikátor `CA` označuje, že operace s jedním qubit je ovladatelné a přiléhající.</span><span class="sxs-lookup"><span data-stu-id="2b041-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2b041-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="2b041-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="2b041-108">singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2b041-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2b041-109">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="2b041-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="2b041-110">registr: t []</span><span class="sxs-lookup"><span data-stu-id="2b041-110">register : 'T[]</span></span>

<span data-ttu-id="2b041-111">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="2b041-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b041-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b041-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2b041-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2b041-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2b041-114">'S</span><span class="sxs-lookup"><span data-stu-id="2b041-114">'T</span></span>

<span data-ttu-id="2b041-115">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="2b041-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="2b041-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="2b041-116">Example</span></span>

<span data-ttu-id="2b041-117">Připravte tři-qubit $ \ket{+} $ stav:</span><span class="sxs-lookup"><span data-stu-id="2b041-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="2b041-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="2b041-118">See Also</span></span>

- [<span data-ttu-id="2b041-119">Microsoft. proApplyToEach. Canon.</span><span class="sxs-lookup"><span data-stu-id="2b041-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)