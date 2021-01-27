---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847385"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="09688-102">CyclicEntanglingLayer – funkce</span><span class="sxs-lookup"><span data-stu-id="09688-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="09688-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="09688-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="09688-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="09688-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="09688-105">Vrátí pole jednotlivě řízených otočení podél dané osy uspořádané cyklicky v rámci registru qubits a parametrizované pomocí různých parametrů modelu.</span><span class="sxs-lookup"><span data-stu-id="09688-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="09688-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="09688-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="09688-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09688-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="09688-108">Počet qubits, které se v dané vrstvě jednalo.</span><span class="sxs-lookup"><span data-stu-id="09688-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="09688-109">osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="09688-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="09688-110">Osa otočení pro každé otočení v dané vrstvě</span><span class="sxs-lookup"><span data-stu-id="09688-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="09688-111">Rozteč: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09688-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="09688-112">Oddělení mezi cílovou a řídicí index pro každé otočení.</span><span class="sxs-lookup"><span data-stu-id="09688-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="09688-113">Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="09688-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="09688-114">Pole qubit řízených otočení, která jsou rozložená cyklicky v rámci registru `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="09688-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>

## <a name="example"></a><span data-ttu-id="09688-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="09688-115">Example</span></span>

<span data-ttu-id="09688-116">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="09688-116">The following are equivalent:</span></span>

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```