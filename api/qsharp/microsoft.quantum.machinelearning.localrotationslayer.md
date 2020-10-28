---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708422"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="8757d-102">LocalRotationsLayer – funkce</span><span class="sxs-lookup"><span data-stu-id="8757d-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="8757d-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8757d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8757d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8757d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8757d-105">Vrátí pole neřízených (jednoduchých-qubit) otočení podél dané osy s jedním otočením pro každý qubit v registru, které je parametrizované pomocí různých parametrů modelu.</span><span class="sxs-lookup"><span data-stu-id="8757d-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="8757d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8757d-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="8757d-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8757d-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8757d-108">Počet qubits, které se v dané vrstvě jednalo.</span><span class="sxs-lookup"><span data-stu-id="8757d-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="8757d-109">osa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="8757d-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="8757d-110">Osa otočení pro každé otočení v dané vrstvě</span><span class="sxs-lookup"><span data-stu-id="8757d-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="8757d-111">Výstup: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="8757d-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="8757d-112">Pole řízených otočení o dané ose, jednu na každé `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="8757d-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>