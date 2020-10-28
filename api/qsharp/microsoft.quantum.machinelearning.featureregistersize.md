---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708344"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="bdff8-102">FeatureRegisterSize – funkce</span><span class="sxs-lookup"><span data-stu-id="bdff8-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="bdff8-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bdff8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="bdff8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bdff8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bdff8-105">Vrátí počet qubits potřebných ke kódování konkrétního vektoru funkce.</span><span class="sxs-lookup"><span data-stu-id="bdff8-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="bdff8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bdff8-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="bdff8-107">Ukázka: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bdff8-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bdff8-108">Vzorový vektor funkce, který se má zakódovat do qubit registru.</span><span class="sxs-lookup"><span data-stu-id="bdff8-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="bdff8-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bdff8-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bdff8-110">Velikost potřebnou ke kódování `sample` do qubit registru vyjádřeného jako počet qubits.</span><span class="sxs-lookup"><span data-stu-id="bdff8-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>