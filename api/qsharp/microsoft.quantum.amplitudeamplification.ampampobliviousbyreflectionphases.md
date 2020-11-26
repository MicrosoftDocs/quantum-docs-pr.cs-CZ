---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpObliviousByReflectionPhases
title: AmpAmpObliviousByReflectionPhases – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpObliviousByReflectionPhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpObliviousByReflectionPhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfrompartialreflections".
ms.openlocfilehash: 58701d7718e0d3b982dc8721eab625f90526973f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191716"
---
# <a name="ampampobliviousbyreflectionphases-function"></a><span data-ttu-id="d741c-102">AmpAmpObliviousByReflectionPhases – funkce</span><span class="sxs-lookup"><span data-stu-id="d741c-102">AmpAmpObliviousByReflectionPhases function</span></span>

<span data-ttu-id="d741c-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d741c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d741c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d741c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="d741c-105">AmpAmpObliviousByReflectionPhases se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="d741c-105">AmpAmpObliviousByReflectionPhases has been deprecated.</span></span> <span data-ttu-id="d741c-106"><xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="d741c-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections> instead.</span></span>
>
> <span data-ttu-id="d741c-107">Používejte @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfrompartialreflections".</span><span class="sxs-lookup"><span data-stu-id="d741c-107">Please use @"microsoft.quantum.amplitudeamplification.obliviousamplitudeamplificationfrompartialreflections".</span></span>



```qsharp
function AmpAmpObliviousByReflectionPhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d741c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="d741c-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="d741c-109">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d741c-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="d741c-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d741c-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="d741c-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d741c-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="d741c-112">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="d741c-112">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>





## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="d741c-113">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="d741c-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

