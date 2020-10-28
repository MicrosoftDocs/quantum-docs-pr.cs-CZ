---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707888"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="2836b-102">ObliviousOracleFromDeterministicStateOracle – funkce</span><span class="sxs-lookup"><span data-stu-id="2836b-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="2836b-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="2836b-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="2836b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2836b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2836b-105">Kombinuje Oracle `DeterministicStateOracle` a `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="2836b-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="2836b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2836b-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="2836b-107">ancillaOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="2836b-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="2836b-108">Příprava stavu Oracle $A $, `DeterministicStateOracle` který působí v registru $a $.</span><span class="sxs-lookup"><span data-stu-id="2836b-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="2836b-109">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="2836b-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="2836b-110">Typ Oracle $U $ `ObliviousOracle` pracuje společně s registrací $a, s $.</span><span class="sxs-lookup"><span data-stu-id="2836b-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="2836b-111">Výstup: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="2836b-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="2836b-112">Typ Oracle $O = UA $ typu `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="2836b-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2836b-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="2836b-113">See Also</span></span>

- [<span data-ttu-id="2836b-114">Microsoft..... Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="2836b-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="2836b-115">Microsoft..... Oracle. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="2836b-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)