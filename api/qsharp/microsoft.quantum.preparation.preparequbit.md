---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Operace PrepareQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708224"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="ad281-102">Operace PrepareQubit</span><span class="sxs-lookup"><span data-stu-id="ad281-102">PrepareQubit operation</span></span>

<span data-ttu-id="ad281-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ad281-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ad281-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad281-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad281-105">Připraví qubit na + 1 ( `Zero` ) eigenstate daného operátoru Pauli.</span><span class="sxs-lookup"><span data-stu-id="ad281-105">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="ad281-106">Pokud se udělí operátor identity, qubit se připraví do maximálního smíšeného stavu.</span><span class="sxs-lookup"><span data-stu-id="ad281-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="ad281-107">Pokud byl původně qubit ve stavu $ \ket {0} $, tato operace připraví qubit v $ + $1 eigenstate daného operátoru Pauli, nebo pro `PauliI` , v případě, že je místo toho ve stavu "maximálního smíšené" (viz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="ad281-107">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="ad281-108">Pokud byl qubit v jiném stavu než $ \ket {0} $, tato operace použije následující brány: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ pro `PauliZ` a <xref:microsoft.quantum.preparation.preparesinglequbitidentity> pro `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="ad281-108">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ad281-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="ad281-109">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="ad281-110">základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ad281-110">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ad281-111">Operátor Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="ad281-111">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ad281-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ad281-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ad281-113">Qubit, který se má připravit.</span><span class="sxs-lookup"><span data-stu-id="ad281-113">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad281-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad281-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

