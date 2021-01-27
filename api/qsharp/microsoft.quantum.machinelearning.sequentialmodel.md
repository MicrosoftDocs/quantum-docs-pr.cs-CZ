---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Uživatelem definovaný typ SequentialModel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854892"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="976e0-102">Uživatelem definovaný typ SequentialModel</span><span class="sxs-lookup"><span data-stu-id="976e0-102">SequentialModel user defined type</span></span>

<span data-ttu-id="976e0-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="976e0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="976e0-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="976e0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="976e0-105">Popisuje model třídění podle počtu stavů složený z sekvence parametrizovaných a řízených otočení, přiřazení úhlů otočení a posunutí mezi dvěma třídami rozpoznávanými modelem.</span><span class="sxs-lookup"><span data-stu-id="976e0-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="976e0-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="976e0-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="976e0-107">Struktura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="976e0-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="976e0-108">Sekvence řízených otočení používaných ke klasifikaci vstupů.</span><span class="sxs-lookup"><span data-stu-id="976e0-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="976e0-109">Parametry: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="976e0-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="976e0-110">Přiřazení úhlů otočení k dané struktuře klasifikace.</span><span class="sxs-lookup"><span data-stu-id="976e0-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="976e0-111">Bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="976e0-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="976e0-112">Posun mezi dvěma třídami rozpoznávanými tímto tříděním.</span><span class="sxs-lookup"><span data-stu-id="976e0-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="976e0-113">Reference</span><span class="sxs-lookup"><span data-stu-id="976e0-113">References</span></span>

- [<span data-ttu-id="976e0-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="976e0-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)