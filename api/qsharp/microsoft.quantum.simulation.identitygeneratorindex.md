---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: b389ca1e0737463e6ccd5ce885b849c6b32d65d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844345"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="40809-102">IdentityGeneratorIndex – funkce</span><span class="sxs-lookup"><span data-stu-id="40809-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="40809-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="40809-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="40809-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40809-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40809-105">Vrátí index generátoru konzistentní s nulovým Hamiltonian, `H = 0` který odpovídá operaci vývoje identity.</span><span class="sxs-lookup"><span data-stu-id="40809-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="40809-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="40809-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="40809-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="40809-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="40809-108">Tento vstup je ignorován a je definován pro konzistenci s <xref:microsoft.quantum.simulation.generatorsystem> uživatelem definovaným typem.</span><span class="sxs-lookup"><span data-stu-id="40809-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="40809-109">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="40809-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="40809-110">Index generátoru představující vývoj pod Hamiltonian $H = $0.</span><span class="sxs-lookup"><span data-stu-id="40809-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>