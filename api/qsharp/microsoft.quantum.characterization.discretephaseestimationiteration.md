---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Operace DiscretePhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698752"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="0f517-102">Operace DiscretePhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="0f517-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="0f517-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="0f517-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="0f517-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f517-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f517-105">Provádí jednu iteraci iteračního (klasického) algoritmu fáze odhadu pomocí celočíselné mocniny jednotkové databáze Oracle.</span><span class="sxs-lookup"><span data-stu-id="0f517-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0f517-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0f517-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="0f517-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="0f517-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="0f517-108">Operace funguje na základě celého čísla a registru, například $U ^ m $ se u daného registru používá, kde $U $ je jednotkou, jejíž fáze má být odhadnuta, a kde $m $ je celočíselný výkon, který je dán pro Oracle.</span><span class="sxs-lookup"><span data-stu-id="0f517-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="0f517-109">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f517-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f517-110">Počet, kolikrát se má daný jednotkový Oracle použít.</span><span class="sxs-lookup"><span data-stu-id="0f517-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="0f517-111">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f517-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f517-112">Úhel, o který se má Invertovat fáze v qubit ovládacího prvku před tím, než se bude chovat v cílovém stavu.</span><span class="sxs-lookup"><span data-stu-id="0f517-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="0f517-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0f517-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0f517-114">Registr stavu, na základě kterého společnost Oracle přijala.</span><span class="sxs-lookup"><span data-stu-id="0f517-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="0f517-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0f517-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0f517-116">Pomocný qubit použitý k řízení aplikace daného Oracle.</span><span class="sxs-lookup"><span data-stu-id="0f517-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f517-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f517-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

