---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Operace PrepareQubit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 84674d70d6a038ceaf1c637b22afa1b724d90795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193518"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="7278d-102">Operace PrepareQubit</span><span class="sxs-lookup"><span data-stu-id="7278d-102">PrepareQubit operation</span></span>

<span data-ttu-id="7278d-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7278d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7278d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7278d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="7278d-105">PrepareQubit se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="7278d-105">PrepareQubit has been deprecated.</span></span> <span data-ttu-id="7278d-106"><xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="7278d-106">Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.</span></span>

<span data-ttu-id="7278d-107">Připraví qubit na + 1 ( `Zero` ) eigenstate daného operátoru Pauli.</span><span class="sxs-lookup"><span data-stu-id="7278d-107">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="7278d-108">Pokud se udělí operátor identity, qubit se připraví do maximálního smíšeného stavu.</span><span class="sxs-lookup"><span data-stu-id="7278d-108">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="7278d-109">Pokud byl původně qubit ve stavu $ \ket {0} $, tato operace připraví qubit v $ + $1 eigenstate daného operátoru Pauli, nebo pro `PauliI` , v případě, že je místo toho ve stavu "maximálního smíšené" (viz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="7278d-109">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="7278d-110">Pokud byl qubit v jiném stavu než $ \ket {0} $, tato operace použije následující brány: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ pro `PauliZ` a <xref:microsoft.quantum.preparation.preparesinglequbitidentity> pro `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="7278d-110">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="7278d-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="7278d-111">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="7278d-112">základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="7278d-112">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="7278d-113">Operátor Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="7278d-113">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="7278d-114">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7278d-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7278d-115">Qubit, který se má připravit.</span><span class="sxs-lookup"><span data-stu-id="7278d-115">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7278d-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7278d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

