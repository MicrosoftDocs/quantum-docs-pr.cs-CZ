---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Operace PrepareSingleQubitIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 12a650568aa5682e8fb6498808d188b154527acb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709028"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="18af2-102">Operace PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="18af2-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="18af2-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="18af2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="18af2-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18af2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18af2-105">Připraví qubit ve stavu maximálního smíšené.</span><span class="sxs-lookup"><span data-stu-id="18af2-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="18af2-106">Připraví zadaný qubit ve stavu $ \boldone/$2 použitím depolarizing kanálu $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \in \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ where $ \sigma \_ i $ je $i $ th Pauli a kde $ \rho $ je operátor hustoty představující smíšený stav.</span><span class="sxs-lookup"><span data-stu-id="18af2-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="18af2-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="18af2-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="18af2-108">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="18af2-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="18af2-109">Qubit, jehož stav má být depolarizace způsobem popsaným výše.</span><span class="sxs-lookup"><span data-stu-id="18af2-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="18af2-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18af2-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="18af2-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="18af2-111">Remarks</span></span>

<span data-ttu-id="18af2-112">Smíšený stav $ \boldone/$2 popisující výsledek použití této operace na stav implicitně popisuje očekávanou hodnotu nad náhodnými možnostmi provedenými v této operaci.</span><span class="sxs-lookup"><span data-stu-id="18af2-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="18af2-113">Pro každou jednotlivou aplikaci tedy tato operace mapuje čistě stavy do čistého stavu, ale funguje tak, jak je popsáno v tématu očekávání.</span><span class="sxs-lookup"><span data-stu-id="18af2-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="18af2-114">Konkrétně tuto operaci lze použít v procesu tomography k měření *nejednotkových* komponent kanálu.</span><span class="sxs-lookup"><span data-stu-id="18af2-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>