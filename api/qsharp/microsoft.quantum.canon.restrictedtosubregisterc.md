---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e03f695ea5943bc2296b0ef1ce613f7835a87c5a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205248"
---
# <a name="restrictedtosubregisterc-function"></a><span data-ttu-id="f4074-102">RestrictedToSubregisterC – funkce</span><span class="sxs-lookup"><span data-stu-id="f4074-102">RestrictedToSubregisterC function</span></span>

<span data-ttu-id="f4074-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4074-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4074-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4074-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4074-105">Omezí operaci na pole indexů registru, tj. na podregistr.</span><span class="sxs-lookup"><span data-stu-id="f4074-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="f4074-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="f4074-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="f4074-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="f4074-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="f4074-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="f4074-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f4074-109">Operace, která se má omezit na podregistr</span><span class="sxs-lookup"><span data-stu-id="f4074-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="f4074-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f4074-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f4074-111">Pole indexů, které určuje, které qubits operace budou omezeny.</span><span class="sxs-lookup"><span data-stu-id="f4074-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit--is-ctl"></a><span data-ttu-id="f4074-112">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="f4074-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="f4074-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="f4074-113">See Also</span></span>

- [<span data-ttu-id="f4074-114">Microsoft. proRestrictedToSubregister. Canon.</span><span class="sxs-lookup"><span data-stu-id="f4074-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)