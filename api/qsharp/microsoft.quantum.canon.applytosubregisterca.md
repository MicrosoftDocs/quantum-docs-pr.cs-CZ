---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: Operace ApplyToSubregisterCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 3eb210debf8980f057ed150f647d545f68734459
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704640"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="b92d0-102">Operace ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="b92d0-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="b92d0-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b92d0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b92d0-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b92d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b92d0-105">Aplikuje operaci na subregistry registru, kde qubits určil pole jeho indexů.</span><span class="sxs-lookup"><span data-stu-id="b92d0-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="b92d0-106">Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.</span><span class="sxs-lookup"><span data-stu-id="b92d0-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b92d0-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="b92d0-107">Input</span></span>

### <a name="op--qubit--unit-ctl--adj"></a><span data-ttu-id="b92d0-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ</span><span class="sxs-lookup"><span data-stu-id="b92d0-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="b92d0-109">Operace, která se má použít pro podregistr</span><span class="sxs-lookup"><span data-stu-id="b92d0-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="b92d0-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b92d0-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b92d0-111">Pole indexů, která označují, která qubits se operace použije.</span><span class="sxs-lookup"><span data-stu-id="b92d0-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b92d0-112">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b92d0-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b92d0-113">Zaregistrujte, na které operace funguje.</span><span class="sxs-lookup"><span data-stu-id="b92d0-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b92d0-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b92d0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b92d0-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="b92d0-115">See Also</span></span>

- [<span data-ttu-id="b92d0-116">Microsoft. proApplyToSubregister. Canon.</span><span class="sxs-lookup"><span data-stu-id="b92d0-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)