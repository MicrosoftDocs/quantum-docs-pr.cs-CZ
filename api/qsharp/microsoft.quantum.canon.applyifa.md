---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operace ApplyIfA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 8bdca1bf286d564dfbb540bc9d63c035d2196f00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845043"
---
# <a name="applyifa-operation"></a><span data-ttu-id="49385-102">Operace ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="49385-102">ApplyIfA operation</span></span>

<span data-ttu-id="49385-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="49385-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="49385-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49385-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="49385-105">Aplikuje v klasickém bitu operaci s sousedním objektem.</span><span class="sxs-lookup"><span data-stu-id="49385-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="49385-106">Popis</span><span class="sxs-lookup"><span data-stu-id="49385-106">Description</span></span>

<span data-ttu-id="49385-107">`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="49385-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="49385-108">`false`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="49385-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="49385-109">Přípona `A` označuje, že operace, která se má použít, je sousední.</span><span class="sxs-lookup"><span data-stu-id="49385-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="49385-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="49385-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="49385-111">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="49385-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="49385-112">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="49385-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="49385-113">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="49385-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="49385-114">logická hodnota, která určuje, zda je použita možnost op.</span><span class="sxs-lookup"><span data-stu-id="49385-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="49385-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="49385-115">target : 'T</span></span>

<span data-ttu-id="49385-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="49385-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49385-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49385-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="49385-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="49385-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="49385-119">'S</span><span class="sxs-lookup"><span data-stu-id="49385-119">'T</span></span>

<span data-ttu-id="49385-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="49385-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="49385-121">Příklad</span><span class="sxs-lookup"><span data-stu-id="49385-121">Example</span></span>

<span data-ttu-id="49385-122">Následující připraví registr qubits do výpočetního stavu, který je reprezentován klasickým bitem řetězce, který byl zadán jako pole `Bool` hodnot:</span><span class="sxs-lookup"><span data-stu-id="49385-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="49385-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="49385-123">See Also</span></span>

- [<span data-ttu-id="49385-124">Microsoft. proApplyIfC. Canon.</span><span class="sxs-lookup"><span data-stu-id="49385-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="49385-125">Microsoft. proApplyIfA. Canon.</span><span class="sxs-lookup"><span data-stu-id="49385-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="49385-126">Microsoft. proApplyIfCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="49385-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)