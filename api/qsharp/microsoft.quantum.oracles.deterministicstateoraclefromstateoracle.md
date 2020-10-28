---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708758"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="086de-102">DeterministicStateOracleFromStateOracle – funkce</span><span class="sxs-lookup"><span data-stu-id="086de-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="086de-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="086de-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="086de-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="086de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="086de-105">Převede typ Oracle typu `StateOracle` na `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="086de-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="086de-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="086de-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="086de-107">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="086de-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="086de-108">Index na příznak qubit `stateOracle` $A $, který explicitně funguje na dvou registrech: příznak $f $ a systém $s $, např. $A \ket {0} \_ f\ket {\ psí} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="086de-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="086de-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="086de-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="086de-110">Příprava stavu Oracle $A $ typu `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="086de-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="086de-111">Výstup: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="086de-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="086de-112">Stejný stav přípravy Oracle $A $, ale nyní `DeterministicStateOracle` je typ, takže funguje v registru, kde $a, s $ již explicitně neoddělené, např.  $A \ket{0\psi} \_ {as} $.</span><span class="sxs-lookup"><span data-stu-id="086de-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="086de-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="086de-113">See Also</span></span>

- [<span data-ttu-id="086de-114">Microsoft..... Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="086de-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="086de-115">Microsoft..... Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="086de-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)