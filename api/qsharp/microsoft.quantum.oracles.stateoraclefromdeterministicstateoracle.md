---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708745"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="c9bbf-102">StateOracleFromDeterministicStateOracle – funkce</span><span class="sxs-lookup"><span data-stu-id="c9bbf-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="c9bbf-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c9bbf-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c9bbf-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9bbf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9bbf-105">Převede typ Oracle typu `DeterministicStateOracle` na `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="c9bbf-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="c9bbf-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c9bbf-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="c9bbf-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="c9bbf-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="c9bbf-108">Příprava stavu Oracle $A $ typu `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="c9bbf-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="c9bbf-109">Výstup: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="c9bbf-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="c9bbf-110">Příprava stavu Oracle $A $, ale nyní je typu `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="c9bbf-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="c9bbf-111">Všimněte si, že index příznaků v této `StateOracle` proměnné je fiktivní proměnná a nemá žádný vliv.</span><span class="sxs-lookup"><span data-stu-id="c9bbf-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9bbf-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="c9bbf-112">See Also</span></span>

- [<span data-ttu-id="c9bbf-113">Microsoft..... Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="c9bbf-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="c9bbf-114">Microsoft..... Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="c9bbf-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)