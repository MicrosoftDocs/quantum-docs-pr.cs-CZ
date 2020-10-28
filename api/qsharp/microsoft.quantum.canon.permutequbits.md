---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operace PermuteQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698920"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="f685d-102">Operace PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="f685d-102">PermuteQubits operation</span></span>

<span data-ttu-id="f685d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f685d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f685d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f685d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f685d-105">Permutes qubits pomocí operace SWAP.</span><span class="sxs-lookup"><span data-stu-id="f685d-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f685d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f685d-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="f685d-107">řazení: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f685d-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f685d-108">Popisuje nové pořadí qubits, kde se teď qubit na indexu i na řazení [i].</span><span class="sxs-lookup"><span data-stu-id="f685d-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f685d-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f685d-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f685d-110">Qubit registrace, na které se má pracovat.</span><span class="sxs-lookup"><span data-stu-id="f685d-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f685d-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f685d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

