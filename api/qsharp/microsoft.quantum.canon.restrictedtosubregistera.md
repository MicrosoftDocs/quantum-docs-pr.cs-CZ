---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: RestrictedToSubregisterA – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 28128641a95c6948b5fa5730bf3bd90aa6bb1ef5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205282"
---
# <a name="restrictedtosubregistera-function"></a><span data-ttu-id="134d7-102">RestrictedToSubregisterA – funkce</span><span class="sxs-lookup"><span data-stu-id="134d7-102">RestrictedToSubregisterA function</span></span>

<span data-ttu-id="134d7-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="134d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="134d7-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="134d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="134d7-105">Omezí operaci na pole indexů registru, tj. na podregistr.</span><span class="sxs-lookup"><span data-stu-id="134d7-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="134d7-106">Modifikátor `A` označuje, že operace je sousední.</span><span class="sxs-lookup"><span data-stu-id="134d7-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="134d7-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="134d7-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="134d7-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="134d7-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="134d7-109">Operace, která se má omezit na podregistr</span><span class="sxs-lookup"><span data-stu-id="134d7-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="134d7-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="134d7-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="134d7-111">Pole indexů, které určuje, které qubits operace budou omezeny.</span><span class="sxs-lookup"><span data-stu-id="134d7-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit--is-adj"></a><span data-ttu-id="134d7-112">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="134d7-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>



## <a name="see-also"></a><span data-ttu-id="134d7-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="134d7-113">See Also</span></span>

- [<span data-ttu-id="134d7-114">Microsoft. proRestrictedToSubregister. Canon.</span><span class="sxs-lookup"><span data-stu-id="134d7-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)