---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operace ContinuousPhaseEstimationIteration
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851897"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="07438-102">Operace ContinuousPhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="07438-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="07438-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="07438-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="07438-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="07438-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="07438-105">Provádí jednu iteraci iteračního (klasického) algoritmu fáze odhadu pomocí libovolného reálného výkonu jednotkové databáze Oracle.</span><span class="sxs-lookup"><span data-stu-id="07438-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="07438-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="07438-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="07438-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="07438-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="07438-108">Operace funguje na dvojitém $t $ a v registru, jako je $U ^ t $ se u daného registru používá, kde $U $ je jednotná, jejíž fáze se má odhadnout, a kde $t $ je celočíselný výkon, který je pro Oracle přidělený.</span><span class="sxs-lookup"><span data-stu-id="07438-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="07438-109">čas: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="07438-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="07438-110">Počet, kolikrát se má daný jednotkový Oracle použít.</span><span class="sxs-lookup"><span data-stu-id="07438-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="07438-111">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="07438-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="07438-112">Úhel, o který se má Invertovat fáze v qubit ovládacího prvku před tím, než se bude chovat v cílovém stavu.</span><span class="sxs-lookup"><span data-stu-id="07438-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="07438-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="07438-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="07438-114">Registr stavu, na základě kterého společnost Oracle přijala.</span><span class="sxs-lookup"><span data-stu-id="07438-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="07438-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="07438-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="07438-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07438-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

