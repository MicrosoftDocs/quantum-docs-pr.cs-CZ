---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Operace ApplyToSubregister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704664"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="5203c-102">Operace ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="5203c-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="5203c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5203c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5203c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5203c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5203c-105">Aplikuje operaci na subregistry registru, kde qubits určil pole jeho indexů.</span><span class="sxs-lookup"><span data-stu-id="5203c-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5203c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5203c-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="5203c-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5203c-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5203c-108">Operace, která se má použít pro podregistr</span><span class="sxs-lookup"><span data-stu-id="5203c-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="5203c-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5203c-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5203c-110">Pole indexů, která označují, která qubits se operace použije.</span><span class="sxs-lookup"><span data-stu-id="5203c-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5203c-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5203c-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5203c-112">Zaregistrujte, na které operace funguje.</span><span class="sxs-lookup"><span data-stu-id="5203c-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5203c-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5203c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5203c-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="5203c-114">See Also</span></span>

- [<span data-ttu-id="5203c-115">Microsoft. proApplyToSubregisterA. Canon.</span><span class="sxs-lookup"><span data-stu-id="5203c-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="5203c-116">Microsoft. proApplyToSubregisterC. Canon.</span><span class="sxs-lookup"><span data-stu-id="5203c-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="5203c-117">Microsoft. proApplyToSubregisterCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="5203c-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)