---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a49b15ac9c3ba9c1959bdead11549c1f37caabf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205367"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="f1940-102">RestrictedToSubregister – funkce</span><span class="sxs-lookup"><span data-stu-id="f1940-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="f1940-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f1940-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f1940-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1940-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1940-105">Omezí operaci na pole indexů registru, tj. na podregistr.</span><span class="sxs-lookup"><span data-stu-id="f1940-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="f1940-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f1940-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="f1940-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1940-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f1940-108">Operace, která se má omezit na podregistr</span><span class="sxs-lookup"><span data-stu-id="f1940-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="f1940-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f1940-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f1940-110">Pole indexů, které určuje, které qubits operace budou omezeny.</span><span class="sxs-lookup"><span data-stu-id="f1940-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="f1940-111">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1940-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="f1940-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="f1940-112">See Also</span></span>

- [<span data-ttu-id="f1940-113">Microsoft. proRestrictedToSubregisterA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f1940-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="f1940-114">Microsoft. proRestrictedToSubregisterC. Canon.</span><span class="sxs-lookup"><span data-stu-id="f1940-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="f1940-115">Microsoft. proRestrictedToSubregisterCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f1940-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)