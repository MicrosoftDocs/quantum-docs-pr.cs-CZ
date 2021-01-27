---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: 8f6c1bf3dfef3152a6ba8eada0980d6940724259
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854970"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="65c44-102">NQubitsRequired – funkce</span><span class="sxs-lookup"><span data-stu-id="65c44-102">NQubitsRequired function</span></span>

<span data-ttu-id="65c44-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="65c44-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="65c44-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="65c44-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="65c44-105">Vrátí počet qubits vyžadovaných k použití daného sekvenčního třídění.</span><span class="sxs-lookup"><span data-stu-id="65c44-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="65c44-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="65c44-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="65c44-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="65c44-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="65c44-108">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="65c44-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="65c44-109">Minimální velikost registru, na kterém může být použit sekvenční třídění.</span><span class="sxs-lookup"><span data-stu-id="65c44-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>