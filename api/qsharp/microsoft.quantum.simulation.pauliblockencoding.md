---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706673"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="d9206-102">PauliBlockEncoding – funkce</span><span class="sxs-lookup"><span data-stu-id="d9206-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="d9206-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d9206-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d9206-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9206-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9206-105">Vytvoří jednotkové kódování bloku pro Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="d9206-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="d9206-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ je popsána na základě součtu Pauli podmínek $P _j $, každý s reálným koeficientem $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="d9206-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="d9206-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d9206-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="d9206-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="d9206-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="d9206-109">A `GeneratorSystem` který popisuje $H $ jako součet podmínek Pauli</span><span class="sxs-lookup"><span data-stu-id="d9206-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="d9206-110">Výstup: ([Double](xref:microsoft.quantum.lang-ref.double);[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="d9206-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="d9206-111">První parametr</span><span class="sxs-lookup"><span data-stu-id="d9206-111">First parameter</span></span>

<span data-ttu-id="d9206-112">Jedna-norma koeficientů $ \Alpha = \ sum_ {j} | \ alpha_j | $</span><span class="sxs-lookup"><span data-stu-id="d9206-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="d9206-113">Druhý parametr</span><span class="sxs-lookup"><span data-stu-id="d9206-113">Second parameter</span></span>

<span data-ttu-id="d9206-114">`BlockEncodingReflection`Jednotková $U $ $H Hamiltonian $.</span><span class="sxs-lookup"><span data-stu-id="d9206-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="d9206-115">Protože tato jednotná operace splňuje $U ^ 2 = I $, je také odraz.</span><span class="sxs-lookup"><span data-stu-id="d9206-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9206-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d9206-116">Remarks</span></span>

<span data-ttu-id="d9206-117">To se získá tím, že se připraví a odpravují stav $ \ sum_ {j}, alpha_j/\Alpha}\ket{j} $ a vytvoří se jednotková a jednotně řízená s vynásobením <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="d9206-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>