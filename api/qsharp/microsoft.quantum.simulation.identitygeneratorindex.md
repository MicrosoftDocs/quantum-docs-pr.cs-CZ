---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229286"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="158f8-102">IdentityGeneratorIndex – funkce</span><span class="sxs-lookup"><span data-stu-id="158f8-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="158f8-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="158f8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="158f8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="158f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="158f8-105">Vrátí index generátoru konzistentní s nulovým Hamiltonian, `H = 0` který odpovídá operaci vývoje identity.</span><span class="sxs-lookup"><span data-stu-id="158f8-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="158f8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="158f8-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="158f8-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="158f8-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="158f8-108">Tento vstup je ignorován a je definován pro konzistenci s <xref:microsoft.quantum.simulation.generatorsystem> uživatelem definovaným typem.</span><span class="sxs-lookup"><span data-stu-id="158f8-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="158f8-109">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="158f8-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="158f8-110">Index generátoru představující vývoj pod Hamiltonian $H = $0.</span><span class="sxs-lookup"><span data-stu-id="158f8-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>