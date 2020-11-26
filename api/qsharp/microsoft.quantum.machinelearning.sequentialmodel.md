---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Uživatelem definovaný typ SequentialModel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196170"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="28d5e-102">Uživatelem definovaný typ SequentialModel</span><span class="sxs-lookup"><span data-stu-id="28d5e-102">SequentialModel user defined type</span></span>

<span data-ttu-id="28d5e-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="28d5e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="28d5e-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="28d5e-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="28d5e-105">Popisuje model třídění podle počtu stavů složený z sekvence parametrizovaných a řízených otočení, přiřazení úhlů otočení a posunutí mezi dvěma třídami rozpoznávanými modelem.</span><span class="sxs-lookup"><span data-stu-id="28d5e-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="28d5e-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="28d5e-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="28d5e-107">Struktura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="28d5e-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="28d5e-108">Sekvence řízených otočení používaných ke klasifikaci vstupů.</span><span class="sxs-lookup"><span data-stu-id="28d5e-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="28d5e-109">Parametry: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="28d5e-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="28d5e-110">Přiřazení úhlů otočení k dané struktuře klasifikace.</span><span class="sxs-lookup"><span data-stu-id="28d5e-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="28d5e-111">Bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="28d5e-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="28d5e-112">Posun mezi dvěma třídami rozpoznávanými tímto tříděním.</span><span class="sxs-lookup"><span data-stu-id="28d5e-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="28d5e-113">Reference</span><span class="sxs-lookup"><span data-stu-id="28d5e-113">References</span></span>

- [<span data-ttu-id="28d5e-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="28d5e-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)