---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operace GetQubitsAvailableToUse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827804"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="66d59-102">Operace GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="66d59-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="66d59-103">Obor názvů: [Microsoft.. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="66d59-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="66d59-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="66d59-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="66d59-105">Vrátí počet qubits aktuálně dostupných k použití.</span><span class="sxs-lookup"><span data-stu-id="66d59-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="66d59-106">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66d59-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66d59-107">Počet qubits, které mohou být přiděleny v `using` příkazu.</span><span class="sxs-lookup"><span data-stu-id="66d59-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="66d59-108">Pokud použitý cílový počítač tyto informace neposkytuje, `-1` vrátí se.</span><span class="sxs-lookup"><span data-stu-id="66d59-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="66d59-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="66d59-109">See Also</span></span>

- [<span data-ttu-id="66d59-110">Microsoft. GetQubitsAvailableToBorrow. Environment.</span><span class="sxs-lookup"><span data-stu-id="66d59-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)