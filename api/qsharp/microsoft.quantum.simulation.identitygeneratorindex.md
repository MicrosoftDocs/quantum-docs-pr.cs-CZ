---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708883"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="23987-102">IdentityGeneratorIndex – funkce</span><span class="sxs-lookup"><span data-stu-id="23987-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="23987-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="23987-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="23987-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23987-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23987-105">Vrátí index generátoru konzistentní s nulovým Hamiltonian, `H = 0` který odpovídá operaci vývoje identity.</span><span class="sxs-lookup"><span data-stu-id="23987-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="23987-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="23987-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="23987-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="23987-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="23987-108">Tento vstup je ignorován a je definován pro konzistenci s <xref:microsoft.quantum.simulation.generatorsystem> uživatelem definovaným typem.</span><span class="sxs-lookup"><span data-stu-id="23987-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="23987-109">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="23987-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="23987-110">Index generátoru představující vývoj pod Hamiltonian $H = $0.</span><span class="sxs-lookup"><span data-stu-id="23987-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>