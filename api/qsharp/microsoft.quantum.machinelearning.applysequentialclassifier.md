---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: Operace ApplySequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: 1b4b4853491489f11f222507bb14b48e941e7859
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706896"
---
# <a name="applysequentialclassifier-operation"></a><span data-ttu-id="ccea7-102">Operace ApplySequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="ccea7-102">ApplySequentialClassifier operation</span></span>

<span data-ttu-id="ccea7-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ccea7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ccea7-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ccea7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ccea7-105">Vzhledem k struktuře a Parametrizace sekvenčního třídění aplikuje klasifikátor na registr qubits.</span><span class="sxs-lookup"><span data-stu-id="ccea7-105">Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.</span></span>

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ccea7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ccea7-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="ccea7-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="ccea7-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="ccea7-108">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ccea7-108">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ccea7-109">Cílový registr, pro který by měl být použit klasifikátor.</span><span class="sxs-lookup"><span data-stu-id="ccea7-109">A target register to which the classifier should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ccea7-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ccea7-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

