---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229983"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="c94b5-102">PurifiedMixedStateRequirements – funkce</span><span class="sxs-lookup"><span data-stu-id="c94b5-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="c94b5-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c94b5-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c94b5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c94b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c94b5-105">Vrátí celkový počet qubits, které musí být přiděleny, aby bylo možné použít operaci vrácenou @"microsoft.quantum.preparation.purifiedmixedstate" .</span><span class="sxs-lookup"><span data-stu-id="c94b5-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="c94b5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c94b5-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="c94b5-107">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c94b5-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c94b5-108">Cílová chyba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="c94b5-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="c94b5-109">nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c94b5-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c94b5-110">Počet koeficientů, které mají být zadány v přípravě smíšeného stavu.</span><span class="sxs-lookup"><span data-stu-id="c94b5-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="c94b5-111">Výstup: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="c94b5-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="c94b5-112">Popis, kolik qubits se vyžaduje v celkovém množství, a pro každý index a registry paměti používané @"microsoft.quantum.preparation.purifiedmixedstate" funkcí.</span><span class="sxs-lookup"><span data-stu-id="c94b5-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="c94b5-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="c94b5-113">See Also</span></span>

- [<span data-ttu-id="c94b5-114">Microsoft. Přípravno. Preparation. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="c94b5-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)