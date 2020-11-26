---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225597"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="414bb-102">_IdentityTimeDependentGeneratorSystem funkce</span><span class="sxs-lookup"><span data-stu-id="414bb-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="414bb-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="414bb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="414bb-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="414bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="414bb-105">Vrátí systém generátoru konzistentní s Hamiltonian `H(s) = 0` , kde `s` je parametr plánu.</span><span class="sxs-lookup"><span data-stu-id="414bb-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="414bb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="414bb-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="414bb-107">Schedule: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="414bb-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="414bb-108">Tento vstup je ignorován a je definován pro konzistenci s <xref:microsoft.quantum.canon.timedependentgeneratorsystem> uživatelem definovaným typem.</span><span class="sxs-lookup"><span data-stu-id="414bb-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="414bb-109">Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="414bb-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="414bb-110">Systém generátoru, který představuje vývoj v rámci Hamiltonian $H (s) = $0 pro všechny $s $.</span><span class="sxs-lookup"><span data-stu-id="414bb-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>