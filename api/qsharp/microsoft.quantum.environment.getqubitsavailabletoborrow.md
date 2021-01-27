---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operace GetQubitsAvailableToBorrow
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853251"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="d8354-102">Operace GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="d8354-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="d8354-103">Obor názvů: [Microsoft.. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="d8354-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="d8354-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d8354-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d8354-105">Vrátí počet qubitsů, které jsou aktuálně k dispozici k vypůjčení.</span><span class="sxs-lookup"><span data-stu-id="d8354-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="d8354-106">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8354-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8354-107">Počet qubits, které by mohly být vypůjčené a nebudou se přidělovat jako součást `borrowing` příkazu.</span><span class="sxs-lookup"><span data-stu-id="d8354-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="d8354-108">Pokud použitý cílový počítač tyto informace neposkytuje, `-1` vrátí se.</span><span class="sxs-lookup"><span data-stu-id="d8354-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8354-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="d8354-109">See Also</span></span>

- [<span data-ttu-id="d8354-110">Microsoft. GetQubitsAvailableToUse. Environment.</span><span class="sxs-lookup"><span data-stu-id="d8354-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)