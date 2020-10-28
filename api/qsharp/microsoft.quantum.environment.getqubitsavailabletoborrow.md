---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operace GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698041"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="9cd04-102">Operace GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="9cd04-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="9cd04-103">Obor názvů: [Microsoft.. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="9cd04-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="9cd04-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9cd04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9cd04-105">Vrátí počet qubitsů, které jsou aktuálně k dispozici k vypůjčení.</span><span class="sxs-lookup"><span data-stu-id="9cd04-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="9cd04-106">To zahrnuje nepoužívané qubits; To znamená, že zahrnuje qubits, který vrátil `GetQubitsAvailableToUse` .</span><span class="sxs-lookup"><span data-stu-id="9cd04-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="9cd04-107">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9cd04-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9cd04-108">Počet qubits, které mohou být přiděleny v `borrowing` příkazu.</span><span class="sxs-lookup"><span data-stu-id="9cd04-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="9cd04-109">Pokud použitý cílový počítač tyto informace neposkytuje, `-1` vrátí se.</span><span class="sxs-lookup"><span data-stu-id="9cd04-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cd04-110">Viz také</span><span class="sxs-lookup"><span data-stu-id="9cd04-110">See Also</span></span>

- [<span data-ttu-id="9cd04-111">Microsoft. GetQubitsAvailableToUse. Environment.</span><span class="sxs-lookup"><span data-stu-id="9cd04-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)