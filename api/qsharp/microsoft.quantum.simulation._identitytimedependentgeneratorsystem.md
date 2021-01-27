---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857989"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="c0824-102">_IdentityTimeDependentGeneratorSystem funkce</span><span class="sxs-lookup"><span data-stu-id="c0824-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="c0824-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c0824-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c0824-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0824-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0824-105">Vrátí systém generátoru konzistentní s Hamiltonian `H(s) = 0` , kde `s` je parametr plánu.</span><span class="sxs-lookup"><span data-stu-id="c0824-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="c0824-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c0824-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="c0824-107">Schedule: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c0824-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c0824-108">Tento vstup je ignorován a je definován pro konzistenci s <xref:microsoft.quantum.canon.timedependentgeneratorsystem> uživatelem definovaným typem.</span><span class="sxs-lookup"><span data-stu-id="c0824-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="c0824-109">Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c0824-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c0824-110">Systém generátoru, který představuje vývoj v rámci Hamiltonian $H (s) = $0 pro všechny $s $.</span><span class="sxs-lookup"><span data-stu-id="c0824-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>