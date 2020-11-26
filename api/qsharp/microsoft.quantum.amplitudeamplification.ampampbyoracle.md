---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByOracle
title: AmpAmpByOracle – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByOracle
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByOracle has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification".
ms.openlocfilehash: bd9cb0ae54d6b09a1945df80b6c62c1e966fd282
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191818"
---
# <a name="ampampbyoracle-function"></a><span data-ttu-id="1c857-102">AmpAmpByOracle – funkce</span><span class="sxs-lookup"><span data-stu-id="1c857-102">AmpAmpByOracle function</span></span>

<span data-ttu-id="1c857-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="1c857-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="1c857-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c857-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="1c857-105">AmpAmpByOracle se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="1c857-105">AmpAmpByOracle has been deprecated.</span></span> <span data-ttu-id="1c857-106"><xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="1c857-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification> instead.</span></span>
>
> <span data-ttu-id="1c857-107">Používejte @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification".</span><span class="sxs-lookup"><span data-stu-id="1c857-107">Please use @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification".</span></span>



```qsharp
function AmpAmpByOracle (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="1c857-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="1c857-108">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="1c857-109">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c857-109">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="stateoracle--stateoracle"></a><span data-ttu-id="1c857-110">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="1c857-110">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="1c857-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c857-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="1c857-112">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="1c857-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

