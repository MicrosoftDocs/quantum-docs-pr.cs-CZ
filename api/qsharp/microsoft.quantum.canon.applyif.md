---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Operace ApplyIf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841869"
---
# <a name="applyif-operation"></a><span data-ttu-id="8a7bd-102">Operace ApplyIf</span><span class="sxs-lookup"><span data-stu-id="8a7bd-102">ApplyIf operation</span></span>

<span data-ttu-id="8a7bd-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8a7bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8a7bd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a7bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a7bd-105">Použije operaci s podmíněným klasickým bitem.</span><span class="sxs-lookup"><span data-stu-id="8a7bd-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="8a7bd-106">Popis</span><span class="sxs-lookup"><span data-stu-id="8a7bd-106">Description</span></span>

<span data-ttu-id="8a7bd-107">`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="8a7bd-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="8a7bd-108">`false`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="8a7bd-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="8a7bd-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="8a7bd-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="8a7bd-110">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a7bd-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8a7bd-111">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="8a7bd-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="8a7bd-112">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8a7bd-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8a7bd-113">logická hodnota, která určuje, zda je použita možnost op.</span><span class="sxs-lookup"><span data-stu-id="8a7bd-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="8a7bd-114">cíl: t</span><span class="sxs-lookup"><span data-stu-id="8a7bd-114">target : 'T</span></span>

<span data-ttu-id="8a7bd-115">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="8a7bd-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8a7bd-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a7bd-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8a7bd-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8a7bd-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8a7bd-118">'S</span><span class="sxs-lookup"><span data-stu-id="8a7bd-118">'T</span></span>

<span data-ttu-id="8a7bd-119">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="8a7bd-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="8a7bd-120">Příklad</span><span class="sxs-lookup"><span data-stu-id="8a7bd-120">Example</span></span>

<span data-ttu-id="8a7bd-121">Následující připraví registr qubits do výpočetního stavu, který je reprezentován klasickým bitem řetězce, který byl zadán jako pole `Bool` hodnot:</span><span class="sxs-lookup"><span data-stu-id="8a7bd-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="8a7bd-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="8a7bd-122">See Also</span></span>

- [<span data-ttu-id="8a7bd-123">Microsoft. proApplyIfC. Canon.</span><span class="sxs-lookup"><span data-stu-id="8a7bd-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="8a7bd-124">Microsoft. proApplyIfA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8a7bd-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="8a7bd-125">Microsoft. proApplyIfCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8a7bd-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)