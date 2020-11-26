---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpObliviousByOraclePhases
title: AmpAmpObliviousByOraclePhases – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpObliviousByOraclePhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpObliviousByOraclePhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfromstatepreparation".
ms.openlocfilehash: 70e31e5ed020babefe78227a666b6c464bddaa1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191750"
---
# <a name="ampampobliviousbyoraclephases-function"></a><span data-ttu-id="d288c-102">AmpAmpObliviousByOraclePhases – funkce</span><span class="sxs-lookup"><span data-stu-id="d288c-102">AmpAmpObliviousByOraclePhases function</span></span>

<span data-ttu-id="d288c-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d288c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d288c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d288c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="d288c-105">AmpAmpObliviousByOraclePhases se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="d288c-105">AmpAmpObliviousByOraclePhases has been deprecated.</span></span> <span data-ttu-id="d288c-106"><xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="d288c-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation> instead.</span></span>
>
> <span data-ttu-id="d288c-107">Používejte @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfromstatepreparation".</span><span class="sxs-lookup"><span data-stu-id="d288c-107">Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfromstatepreparation".</span></span>



```qsharp
function AmpAmpObliviousByOraclePhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d288c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="d288c-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="d288c-109">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d288c-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="d288c-110">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="d288c-110">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>




### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="d288c-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="d288c-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="d288c-112">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d288c-112">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="d288c-113">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="d288c-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

