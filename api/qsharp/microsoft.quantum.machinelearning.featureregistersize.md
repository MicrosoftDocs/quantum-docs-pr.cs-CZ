---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196408"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="b0d58-102">FeatureRegisterSize – funkce</span><span class="sxs-lookup"><span data-stu-id="b0d58-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="b0d58-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b0d58-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b0d58-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b0d58-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b0d58-105">Vrátí počet qubits potřebných ke kódování konkrétního vektoru funkce.</span><span class="sxs-lookup"><span data-stu-id="b0d58-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="b0d58-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b0d58-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="b0d58-107">Ukázka: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b0d58-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b0d58-108">Vzorový vektor funkce, který se má zakódovat do qubit registru.</span><span class="sxs-lookup"><span data-stu-id="b0d58-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="b0d58-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0d58-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0d58-110">Velikost potřebnou ke kódování `sample` do qubit registru vyjádřeného jako počet qubits.</span><span class="sxs-lookup"><span data-stu-id="b0d58-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>