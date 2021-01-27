---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Uživatelem definovaný typ ControlledRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847398"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="d6807-102">Uživatelem definovaný typ ControlledRotation</span><span class="sxs-lookup"><span data-stu-id="d6807-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="d6807-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d6807-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d6807-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d6807-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d6807-105">Popisuje řízené otočení z pohledu na své cílové a řídicí indexy, osu natočení a index do vektoru parametru modelu.</span><span class="sxs-lookup"><span data-stu-id="d6807-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="d6807-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="d6807-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="d6807-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6807-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6807-108">Index cílového qubit pro toto řízené otočení.</span><span class="sxs-lookup"><span data-stu-id="d6807-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="d6807-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d6807-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d6807-110">Pole qubity ovládacího prvku pro toto otočení.</span><span class="sxs-lookup"><span data-stu-id="d6807-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="d6807-111">Osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="d6807-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="d6807-112">Osa pro toto otočení</span><span class="sxs-lookup"><span data-stu-id="d6807-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="d6807-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6807-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6807-114">Index na vektor parametru modelu popisující úhel pro toto otočení.</span><span class="sxs-lookup"><span data-stu-id="d6807-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="example"></a><span data-ttu-id="d6807-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="d6807-115">Example</span></span>

<span data-ttu-id="d6807-116">Následující představuje rotaci o $X $ osa prvního qubit v registru, řízená na druhé qubit a s úhlem daným čtvrtým parametrem sekvenčního modelu:</span><span class="sxs-lookup"><span data-stu-id="d6807-116">The following represents a rotation about the $X$-axis of the first qubit in a register, controlled on the second qubit, and with an angle given by the fourth parameter in a sequential model:</span></span>

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a><span data-ttu-id="d6807-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d6807-117">Remarks</span></span>

<span data-ttu-id="d6807-118">Neřízené otočení lze reprezentovat nastavením `ControlIndices` na prázdné pole indexů `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="d6807-118">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>