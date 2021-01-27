---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: Uživatelem definovaný typ TimeDependentGeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: dbbbb2b67dcf191c74e593f61eb894192acb4d48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854729"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a><span data-ttu-id="6f6d1-102">Uživatelem definovaný typ TimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="6f6d1-102">TimeDependentGeneratorSystem user defined type</span></span>

<span data-ttu-id="6f6d1-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6f6d1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6f6d1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f6d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f6d1-105">Představuje časově závislý dynamický generátor jako funkci od času k hodnotě dynamického generátoru v daném čase.</span><span class="sxs-lookup"><span data-stu-id="6f6d1-105">Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.</span></span>

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

