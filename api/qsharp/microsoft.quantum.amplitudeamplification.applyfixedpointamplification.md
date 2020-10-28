---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Operace ApplyFixedPointAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707755"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="4d421-102">Operace ApplyFixedPointAmplification</span><span class="sxs-lookup"><span data-stu-id="4d421-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="4d421-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="4d421-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="4d421-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d421-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d421-105">Fixed-Point algoritmus zesílení amplitudy</span><span class="sxs-lookup"><span data-stu-id="4d421-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="4d421-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4d421-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="4d421-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="4d421-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="4d421-108">Jednotkový Oracle, který připraví stav spuštění.</span><span class="sxs-lookup"><span data-stu-id="4d421-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="4d421-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4d421-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4d421-110">Qubit registraci</span><span class="sxs-lookup"><span data-stu-id="4d421-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d421-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d421-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4d421-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4d421-112">Remarks</span></span>

<span data-ttu-id="4d421-113">StartQubits musí být ve stavu $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="4d421-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="4d421-114">Tato operace provede iteraci několika dotazů v rámci pravomoci $2 $, dokud nedosáhnete maximálního počtu dotazů, nebo pokud cílový stav není nalezen.</span><span class="sxs-lookup"><span data-stu-id="4d421-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>