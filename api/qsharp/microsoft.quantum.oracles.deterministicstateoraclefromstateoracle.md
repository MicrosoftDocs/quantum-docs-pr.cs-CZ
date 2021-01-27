---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: af545a7d6e82e654ee36ab3ba77c8f8be3384b96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854562"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="bf891-102">DeterministicStateOracleFromStateOracle – funkce</span><span class="sxs-lookup"><span data-stu-id="bf891-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="bf891-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="bf891-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="bf891-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf891-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf891-105">Převede typ Oracle typu `StateOracle` na `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="bf891-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="bf891-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bf891-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="bf891-107">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bf891-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bf891-108">Index na příznak qubit `stateOracle` $A $, který explicitně funguje na dvou registrech: příznak $f $ a systém $s $, např. $A \ket {0} \_ f\ket {\ psí} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="bf891-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="bf891-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="bf891-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="bf891-110">Příprava stavu Oracle $A $ typu `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="bf891-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="bf891-111">Výstup: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="bf891-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="bf891-112">Stejný stav přípravy Oracle $A $, ale nyní `DeterministicStateOracle` je typ, takže funguje v registru, kde $a, s $ již explicitně neoddělené, např.  $A \ket{0\psi} \_ {as} $.</span><span class="sxs-lookup"><span data-stu-id="bf891-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf891-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="bf891-113">See Also</span></span>

- [<span data-ttu-id="bf891-114">Microsoft..... Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="bf891-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="bf891-115">Microsoft..... Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="bf891-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)