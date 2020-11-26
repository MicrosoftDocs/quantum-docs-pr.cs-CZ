---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 1549f24427f19bacbadf72e00c1c0181b64bcb73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211725"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="1ef74-102">LocalRotationsLayer – funkce</span><span class="sxs-lookup"><span data-stu-id="1ef74-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="1ef74-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1ef74-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1ef74-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1ef74-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="1ef74-105">Vrátí pole neřízených (jednoduchých-qubit) otočení podél dané osy s jedním otočením pro každý qubit v registru, které je parametrizované pomocí různých parametrů modelu.</span><span class="sxs-lookup"><span data-stu-id="1ef74-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="1ef74-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="1ef74-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="1ef74-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1ef74-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1ef74-108">Počet qubits, které se v dané vrstvě jednalo.</span><span class="sxs-lookup"><span data-stu-id="1ef74-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="1ef74-109">osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="1ef74-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="1ef74-110">Osa otočení pro každé otočení v dané vrstvě</span><span class="sxs-lookup"><span data-stu-id="1ef74-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="1ef74-111">Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="1ef74-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="1ef74-112">Pole řízených otočení o dané ose, jednu na každé `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="1ef74-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>