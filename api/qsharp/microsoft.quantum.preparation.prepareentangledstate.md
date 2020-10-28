---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Operace PrepareEntangledState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707869"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="98bb9-102">Operace PrepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="98bb9-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="98bb9-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="98bb9-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="98bb9-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="98bb9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="98bb9-105">Entangles dva Registry qubit.</span><span class="sxs-lookup"><span data-stu-id="98bb9-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="98bb9-106">To znamená, že dané dva Registry připraví maximální entangled stav $ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ mezi každou dvojicí qubits v příslušných registrech za předpokladu, že každý registr začíná ve stavu $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="98bb9-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="98bb9-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="98bb9-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="98bb9-108">Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="98bb9-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="98bb9-109">Pole qubit ve stavu $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="98bb9-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="98bb9-110">Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="98bb9-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="98bb9-111">Pole qubit ve stavu $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="98bb9-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="98bb9-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98bb9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

