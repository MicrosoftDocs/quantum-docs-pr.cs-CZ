---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Operace ApplyIfC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: ef16b23349b604d174e72d9ae06d2052e2ab60f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841865"
---
# <a name="applyifc-operation"></a><span data-ttu-id="f1839-102">Operace ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="f1839-102">ApplyIfC operation</span></span>

<span data-ttu-id="f1839-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f1839-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f1839-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1839-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1839-105">Aplikuje naovladatelné operace s podmíněným klasickým bitem.</span><span class="sxs-lookup"><span data-stu-id="f1839-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="f1839-106">Popis</span><span class="sxs-lookup"><span data-stu-id="f1839-106">Description</span></span>

<span data-ttu-id="f1839-107">`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="f1839-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="f1839-108">`false`V případě, že se nic nestane s `target` .</span><span class="sxs-lookup"><span data-stu-id="f1839-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f1839-109">Přípona `C` označuje, že operace, která se má použít, je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="f1839-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="f1839-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="f1839-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f1839-111">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="f1839-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f1839-112">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="f1839-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="f1839-113">bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f1839-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f1839-114">logická hodnota, která určuje, zda je použita možnost op.</span><span class="sxs-lookup"><span data-stu-id="f1839-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="f1839-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="f1839-115">target : 'T</span></span>

<span data-ttu-id="f1839-116">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="f1839-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1839-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1839-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f1839-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f1839-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f1839-119">'S</span><span class="sxs-lookup"><span data-stu-id="f1839-119">'T</span></span>

<span data-ttu-id="f1839-120">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="f1839-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="f1839-121">Příklad</span><span class="sxs-lookup"><span data-stu-id="f1839-121">Example</span></span>

<span data-ttu-id="f1839-122">Následující připraví registr qubits do výpočetního stavu, který je reprezentován klasickým bitem řetězce, který byl zadán jako pole `Bool` hodnot:</span><span class="sxs-lookup"><span data-stu-id="f1839-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="f1839-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="f1839-123">See Also</span></span>

- [<span data-ttu-id="f1839-124">Microsoft. proApplyIfC. Canon.</span><span class="sxs-lookup"><span data-stu-id="f1839-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="f1839-125">Microsoft. proApplyIfA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f1839-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="f1839-126">Microsoft. proApplyIfCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f1839-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)