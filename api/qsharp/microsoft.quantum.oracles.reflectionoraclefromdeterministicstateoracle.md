---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707870"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="f25b1-102">ReflectionOracleFromDeterministicStateOracle – funkce</span><span class="sxs-lookup"><span data-stu-id="f25b1-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="f25b1-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="f25b1-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="f25b1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f25b1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f25b1-105">Sestaví reflexi o daném stavu od Oracle.</span><span class="sxs-lookup"><span data-stu-id="f25b1-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="f25b1-106">Popis</span><span class="sxs-lookup"><span data-stu-id="f25b1-106">Description</span></span>

<span data-ttu-id="f25b1-107">Vzhledem k deterministickému přípravné přípravě Oracle reprezentované jednou jednotkovou maticí $O $ je výsledkem této funkce Oracle, který používá odraz kolem stavu $ \ket{\psi} $ připraveného Oracle $O $;. To znamená, že se jedná o stav $ \ket{\psi} $, který $O \ket {0} = \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="f25b1-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="f25b1-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="f25b1-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="f25b1-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="f25b1-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="f25b1-110">Oracle, který připraví kopie stavu $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="f25b1-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="f25b1-111">Výstup: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="f25b1-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="f25b1-112">Oracle, který odráží stav $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="f25b1-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="f25b1-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="f25b1-113">See Also</span></span>

- [<span data-ttu-id="f25b1-114">Microsoft..... Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="f25b1-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="f25b1-115">Microsoft..... Oracle. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="f25b1-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)