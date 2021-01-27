---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848431"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="623b6-102">FeatureRegisterSize – funkce</span><span class="sxs-lookup"><span data-stu-id="623b6-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="623b6-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="623b6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="623b6-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="623b6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="623b6-105">Vrátí počet qubits potřebných ke kódování konkrétního vektoru funkce.</span><span class="sxs-lookup"><span data-stu-id="623b6-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="623b6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="623b6-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="623b6-107">Ukázka: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="623b6-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="623b6-108">Vzorový vektor funkce, který se má zakódovat do qubit registru.</span><span class="sxs-lookup"><span data-stu-id="623b6-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="623b6-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="623b6-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="623b6-110">Velikost potřebnou ke kódování `sample` do qubit registru vyjádřeného jako počet qubits.</span><span class="sxs-lookup"><span data-stu-id="623b6-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>