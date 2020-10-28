---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: Operace ApplyToSubregisterA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: e0c546b768320ce43e7b44242d15838194e1089d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704657"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="71d21-102">Operace ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="71d21-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="71d21-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71d21-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71d21-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71d21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71d21-105">Aplikuje operaci na subregistry registru, kde qubits určil pole jeho indexů.</span><span class="sxs-lookup"><span data-stu-id="71d21-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="71d21-106">Modifikátor `A` označuje, že operace je sousední.</span><span class="sxs-lookup"><span data-stu-id="71d21-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="71d21-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="71d21-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="71d21-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="71d21-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="71d21-109">Operace, která se má použít pro podregistr</span><span class="sxs-lookup"><span data-stu-id="71d21-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="71d21-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="71d21-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="71d21-111">Pole indexů, která označují, která qubits se operace použije.</span><span class="sxs-lookup"><span data-stu-id="71d21-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="71d21-112">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="71d21-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="71d21-113">Zaregistrujte, na které operace funguje.</span><span class="sxs-lookup"><span data-stu-id="71d21-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71d21-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71d21-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="71d21-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="71d21-115">See Also</span></span>

- [<span data-ttu-id="71d21-116">Microsoft. proApplyToSubregister. Canon.</span><span class="sxs-lookup"><span data-stu-id="71d21-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)