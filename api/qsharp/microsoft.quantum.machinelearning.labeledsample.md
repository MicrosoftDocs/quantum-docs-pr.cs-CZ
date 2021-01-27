---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Uživatelem definovaný typ LabeledSample
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846965"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="00e3b-102">Uživatelem definovaný typ LabeledSample</span><span class="sxs-lookup"><span data-stu-id="00e3b-102">LabeledSample user defined type</span></span>

<span data-ttu-id="00e3b-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="00e3b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="00e3b-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="00e3b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="00e3b-105">Vzorek označený třídou, do které patří ukázka.</span><span class="sxs-lookup"><span data-stu-id="00e3b-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="00e3b-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="00e3b-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="00e3b-107">Funkce: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="00e3b-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="00e3b-108">Vektor funkcí pro danou ukázku.</span><span class="sxs-lookup"><span data-stu-id="00e3b-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="00e3b-109">Popisek: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00e3b-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00e3b-110">Celočíselný popisek třídy, ke které patří tato ukázka.</span><span class="sxs-lookup"><span data-stu-id="00e3b-110">An integer label for the class to which this sample belongs.</span></span>