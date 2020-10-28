---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: Operace ApplyToSubregisterC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: ba5be1e7e822197eb76aac029be8617a70d51ddb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704648"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="133af-102">Operace ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="133af-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="133af-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="133af-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="133af-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="133af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="133af-105">Aplikuje operaci na subregistry registru, kde qubits určil pole jeho indexů.</span><span class="sxs-lookup"><span data-stu-id="133af-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="133af-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="133af-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="133af-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="133af-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="133af-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = seznam Ctl pro> [jednotku](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="133af-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="133af-109">Operace, která se má použít pro podregistr</span><span class="sxs-lookup"><span data-stu-id="133af-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="133af-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="133af-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="133af-111">Pole indexů, která označují, která qubits se operace použije.</span><span class="sxs-lookup"><span data-stu-id="133af-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="133af-112">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="133af-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="133af-113">Zaregistrujte, na které operace funguje.</span><span class="sxs-lookup"><span data-stu-id="133af-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="133af-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="133af-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="133af-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="133af-115">See Also</span></span>

- [<span data-ttu-id="133af-116">Microsoft. proApplyToSubregister. Canon.</span><span class="sxs-lookup"><span data-stu-id="133af-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)