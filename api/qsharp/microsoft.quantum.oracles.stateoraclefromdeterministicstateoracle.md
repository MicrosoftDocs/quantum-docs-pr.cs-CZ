---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: f3c225ee185b4b70ab0ea60af6f0fb154288d9bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193807"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="98d19-102">StateOracleFromDeterministicStateOracle – funkce</span><span class="sxs-lookup"><span data-stu-id="98d19-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="98d19-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="98d19-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="98d19-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98d19-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98d19-105">Převede typ Oracle typu `DeterministicStateOracle` na `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="98d19-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="98d19-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="98d19-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="98d19-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="98d19-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="98d19-108">Příprava stavu Oracle $A $ typu `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="98d19-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="98d19-109">Výstup: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="98d19-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="98d19-110">Příprava stavu Oracle $A $, ale nyní je typu `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="98d19-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="98d19-111">Všimněte si, že index příznaků v této `StateOracle` proměnné je fiktivní proměnná a nemá žádný vliv.</span><span class="sxs-lookup"><span data-stu-id="98d19-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="98d19-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="98d19-112">See Also</span></span>

- [<span data-ttu-id="98d19-113">Microsoft..... Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="98d19-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="98d19-114">Microsoft..... Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="98d19-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)