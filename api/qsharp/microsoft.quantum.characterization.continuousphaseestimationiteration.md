---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operace ContinuousPhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698753"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="bdd0e-102">Operace ContinuousPhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="bdd0e-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="bdd0e-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="bdd0e-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="bdd0e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bdd0e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bdd0e-105">Provádí jednu iteraci iteračního (klasického) algoritmu fáze odhadu pomocí libovolného reálného výkonu jednotkové databáze Oracle.</span><span class="sxs-lookup"><span data-stu-id="bdd0e-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="bdd0e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bdd0e-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="bdd0e-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="bdd0e-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="bdd0e-108">Operace funguje na dvojitém $t $ a v registru, jako je $U ^ t $ se u daného registru používá, kde $U $ je jednotná, jejíž fáze se má odhadnout, a kde $t $ je celočíselný výkon, který je pro Oracle přidělený.</span><span class="sxs-lookup"><span data-stu-id="bdd0e-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="bdd0e-109">čas: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bdd0e-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bdd0e-110">Počet, kolikrát se má daný jednotkový Oracle použít.</span><span class="sxs-lookup"><span data-stu-id="bdd0e-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="bdd0e-111">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bdd0e-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bdd0e-112">Úhel, o který se má Invertovat fáze v qubit ovládacího prvku před tím, než se bude chovat v cílovém stavu.</span><span class="sxs-lookup"><span data-stu-id="bdd0e-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="bdd0e-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bdd0e-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bdd0e-114">Registr stavu, na základě kterého společnost Oracle přijala.</span><span class="sxs-lookup"><span data-stu-id="bdd0e-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="bdd0e-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bdd0e-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="bdd0e-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bdd0e-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

