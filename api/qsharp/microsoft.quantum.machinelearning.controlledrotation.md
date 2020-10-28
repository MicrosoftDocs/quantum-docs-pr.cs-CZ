---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Uživatelem definovaný typ ControlledRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697692"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="674f6-102">Uživatelem definovaný typ ControlledRotation</span><span class="sxs-lookup"><span data-stu-id="674f6-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="674f6-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="674f6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="674f6-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="674f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="674f6-105">Popisuje řízené otočení z pohledu na své cílové a řídicí indexy, osu natočení a index do vektoru parametru modelu.</span><span class="sxs-lookup"><span data-stu-id="674f6-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="674f6-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="674f6-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="674f6-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="674f6-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="674f6-108">Index cílového qubit pro toto řízené otočení.</span><span class="sxs-lookup"><span data-stu-id="674f6-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="674f6-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="674f6-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="674f6-110">Pole qubity ovládacího prvku pro toto otočení.</span><span class="sxs-lookup"><span data-stu-id="674f6-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="674f6-111">Osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="674f6-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="674f6-112">Osa pro toto otočení</span><span class="sxs-lookup"><span data-stu-id="674f6-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="674f6-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="674f6-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="674f6-114">Index na vektor parametru modelu popisující úhel pro toto otočení.</span><span class="sxs-lookup"><span data-stu-id="674f6-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="674f6-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="674f6-115">Remarks</span></span>

<span data-ttu-id="674f6-116">Neřízené otočení lze reprezentovat nastavením `ControlIndices` na prázdné pole indexů `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="674f6-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>