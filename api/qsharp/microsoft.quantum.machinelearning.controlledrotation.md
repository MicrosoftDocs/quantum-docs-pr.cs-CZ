---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Uživatelem definovaný typ ControlledRotation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196561"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="d3ef0-102">Uživatelem definovaný typ ControlledRotation</span><span class="sxs-lookup"><span data-stu-id="d3ef0-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="d3ef0-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d3ef0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d3ef0-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d3ef0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d3ef0-105">Popisuje řízené otočení z pohledu na své cílové a řídicí indexy, osu natočení a index do vektoru parametru modelu.</span><span class="sxs-lookup"><span data-stu-id="d3ef0-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="d3ef0-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="d3ef0-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="d3ef0-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3ef0-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3ef0-108">Index cílového qubit pro toto řízené otočení.</span><span class="sxs-lookup"><span data-stu-id="d3ef0-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="d3ef0-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d3ef0-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d3ef0-110">Pole qubity ovládacího prvku pro toto otočení.</span><span class="sxs-lookup"><span data-stu-id="d3ef0-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="d3ef0-111">Osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="d3ef0-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="d3ef0-112">Osa pro toto otočení</span><span class="sxs-lookup"><span data-stu-id="d3ef0-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="d3ef0-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3ef0-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3ef0-114">Index na vektor parametru modelu popisující úhel pro toto otočení.</span><span class="sxs-lookup"><span data-stu-id="d3ef0-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3ef0-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d3ef0-115">Remarks</span></span>

<span data-ttu-id="d3ef0-116">Neřízené otočení lze reprezentovat nastavením `ControlIndices` na prázdné pole indexů `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="d3ef0-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>