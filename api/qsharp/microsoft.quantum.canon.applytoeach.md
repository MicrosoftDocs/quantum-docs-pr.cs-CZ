---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Operace ApplyToEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844629"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="f49c2-102">Operace ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="f49c2-102">ApplyToEach operation</span></span>

<span data-ttu-id="f49c2-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f49c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f49c2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f49c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f49c2-105">Aplikuje jednu qubit operaci na každý prvek v registru.</span><span class="sxs-lookup"><span data-stu-id="f49c2-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f49c2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f49c2-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="f49c2-107">singleElementOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f49c2-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f49c2-108">Operace, která se má použít u každého qubit</span><span class="sxs-lookup"><span data-stu-id="f49c2-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f49c2-109">registr: t []</span><span class="sxs-lookup"><span data-stu-id="f49c2-109">register : 'T[]</span></span>

<span data-ttu-id="f49c2-110">Pole qubits, na které se má použít daná operace</span><span class="sxs-lookup"><span data-stu-id="f49c2-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f49c2-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f49c2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f49c2-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f49c2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f49c2-113">'S</span><span class="sxs-lookup"><span data-stu-id="f49c2-113">'T</span></span>

<span data-ttu-id="f49c2-114">Cíl, na kterém operace funguje.</span><span class="sxs-lookup"><span data-stu-id="f49c2-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="f49c2-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="f49c2-115">Example</span></span>

<span data-ttu-id="f49c2-116">Připravte tři-qubit $ \ket{+} $ stav:</span><span class="sxs-lookup"><span data-stu-id="f49c2-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="f49c2-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="f49c2-117">See Also</span></span>

- [<span data-ttu-id="f49c2-118">Microsoft. proApplyToEachC. Canon.</span><span class="sxs-lookup"><span data-stu-id="f49c2-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="f49c2-119">Microsoft. proApplyToEachA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f49c2-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="f49c2-120">Microsoft. proApplyToEachCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f49c2-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)