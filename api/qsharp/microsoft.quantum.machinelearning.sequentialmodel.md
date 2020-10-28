---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Uživatelem definovaný typ SequentialModel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707960"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="f3249-102">Uživatelem definovaný typ SequentialModel</span><span class="sxs-lookup"><span data-stu-id="f3249-102">SequentialModel user defined type</span></span>

<span data-ttu-id="f3249-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f3249-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f3249-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3249-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3249-105">Popisuje model třídění podle počtu stavů složený z sekvence parametrizovaných a řízených otočení, přiřazení úhlů otočení a posunutí mezi dvěma třídami rozpoznávanými modelem.</span><span class="sxs-lookup"><span data-stu-id="f3249-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="f3249-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="f3249-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="f3249-107">Struktura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="f3249-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="f3249-108">Sekvence řízených otočení používaných ke klasifikaci vstupů.</span><span class="sxs-lookup"><span data-stu-id="f3249-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="f3249-109">Parametry: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f3249-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f3249-110">Přiřazení úhlů otočení k dané struktuře klasifikace.</span><span class="sxs-lookup"><span data-stu-id="f3249-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="f3249-111">Bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3249-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f3249-112">Posun mezi dvěma třídami rozpoznávanými tímto tříděním.</span><span class="sxs-lookup"><span data-stu-id="f3249-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="f3249-113">Odkazy</span><span class="sxs-lookup"><span data-stu-id="f3249-113">References</span></span>

- [<span data-ttu-id="f3249-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="f3249-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)