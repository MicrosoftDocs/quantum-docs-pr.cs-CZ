---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operace GetQubitsAvailableToUse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201406"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="ac3ef-102">Operace GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="ac3ef-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="ac3ef-103">Obor názvů: [Microsoft.. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="ac3ef-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="ac3ef-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ac3ef-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ac3ef-105">Vrátí počet qubits aktuálně dostupných k použití.</span><span class="sxs-lookup"><span data-stu-id="ac3ef-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="ac3ef-106">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac3ef-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac3ef-107">Počet qubits, které mohou být přiděleny v `using` příkazu.</span><span class="sxs-lookup"><span data-stu-id="ac3ef-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="ac3ef-108">Pokud použitý cílový počítač tyto informace neposkytuje, `-1` vrátí se.</span><span class="sxs-lookup"><span data-stu-id="ac3ef-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac3ef-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="ac3ef-109">See Also</span></span>

- [<span data-ttu-id="ac3ef-110">Microsoft. GetQubitsAvailableToBorrow. Environment.</span><span class="sxs-lookup"><span data-stu-id="ac3ef-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)