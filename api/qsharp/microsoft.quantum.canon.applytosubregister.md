---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Operace ApplyToSubregister
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: d4589edaadf59bbfff432bf49be2ce14fcff6ed1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208104"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="231bb-102">Operace ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="231bb-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="231bb-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="231bb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="231bb-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="231bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="231bb-105">Aplikuje operaci na subregistry registru, kde qubits určil pole jeho indexů.</span><span class="sxs-lookup"><span data-stu-id="231bb-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="231bb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="231bb-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="231bb-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="231bb-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="231bb-108">Operace, která se má použít pro podregistr</span><span class="sxs-lookup"><span data-stu-id="231bb-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="231bb-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="231bb-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="231bb-110">Pole indexů, která označují, která qubits se operace použije.</span><span class="sxs-lookup"><span data-stu-id="231bb-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="231bb-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="231bb-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="231bb-112">Zaregistrujte, na které operace funguje.</span><span class="sxs-lookup"><span data-stu-id="231bb-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="231bb-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="231bb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="231bb-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="231bb-114">See Also</span></span>

- [<span data-ttu-id="231bb-115">Microsoft. proApplyToSubregisterA. Canon.</span><span class="sxs-lookup"><span data-stu-id="231bb-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="231bb-116">Microsoft. proApplyToSubregisterC. Canon.</span><span class="sxs-lookup"><span data-stu-id="231bb-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="231bb-117">Microsoft. proApplyToSubregisterCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="231bb-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)