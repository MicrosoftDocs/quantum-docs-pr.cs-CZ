---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operace GetQubitsAvailableToBorrow
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201457"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="fc5c7-102">Operace GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="fc5c7-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="fc5c7-103">Obor názvů: [Microsoft.. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="fc5c7-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="fc5c7-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fc5c7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fc5c7-105">Vrátí počet qubitsů, které jsou aktuálně k dispozici k vypůjčení.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="fc5c7-106">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc5c7-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc5c7-107">Počet qubits, které by mohly být vypůjčené a nebudou se přidělovat jako součást `borrowing` příkazu.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="fc5c7-108">Pokud použitý cílový počítač tyto informace neposkytuje, `-1` vrátí se.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc5c7-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="fc5c7-109">See Also</span></span>

- [<span data-ttu-id="fc5c7-110">Microsoft. GetQubitsAvailableToUse. Environment.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)