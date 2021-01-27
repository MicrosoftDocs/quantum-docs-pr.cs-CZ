---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Operace ApplyFixedPointAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847230"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="4d6d2-102">Operace ApplyFixedPointAmplification</span><span class="sxs-lookup"><span data-stu-id="4d6d2-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="4d6d2-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="4d6d2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="4d6d2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d6d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d6d2-105">Fixed-Point algoritmus zesílení amplitudy</span><span class="sxs-lookup"><span data-stu-id="4d6d2-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="4d6d2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4d6d2-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="4d6d2-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="4d6d2-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="4d6d2-108">Jednotkový Oracle, který připraví stav spuštění.</span><span class="sxs-lookup"><span data-stu-id="4d6d2-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="4d6d2-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4d6d2-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4d6d2-110">Qubit registraci</span><span class="sxs-lookup"><span data-stu-id="4d6d2-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d6d2-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d6d2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4d6d2-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4d6d2-112">Remarks</span></span>

<span data-ttu-id="4d6d2-113">StartQubits musí být ve stavu $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="4d6d2-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="4d6d2-114">Tato operace provede iteraci několika dotazů v rámci pravomoci $2 $, dokud nedosáhnete maximálního počtu dotazů, nebo pokud cílový stav není nalezen.</span><span class="sxs-lookup"><span data-stu-id="4d6d2-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>