---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Operace PreparePauliEigenstate
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: 473bb2fa4429a14f69bcae4573354aad87dc37df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854346"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="49e0c-102">Operace PreparePauliEigenstate</span><span class="sxs-lookup"><span data-stu-id="49e0c-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="49e0c-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="49e0c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="49e0c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49e0c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="49e0c-105">Připraví qubit v kladné eigenstate daného operátoru Pauli.</span><span class="sxs-lookup"><span data-stu-id="49e0c-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="49e0c-106">Pokud se udělí operátor identity, qubit se připraví do maximálního smíšeného stavu.</span><span class="sxs-lookup"><span data-stu-id="49e0c-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="49e0c-107">Popis</span><span class="sxs-lookup"><span data-stu-id="49e0c-107">Description</span></span>

<span data-ttu-id="49e0c-108">Pokud byl původně qubit ve stavu $ \ket {0} $, tato operace připraví qubit v $ + $1 eigenstate daného operátoru Pauli, nebo pro `PauliI` , v případě, že je místo toho ve stavu "maximálního smíšené" (viz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="49e0c-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="49e0c-109">Pokud byl qubit v jiném stavu než $ \ket {0} $, tato operace použije následující brány: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ pro `PauliZ` a <xref:microsoft.quantum.preparation.preparesinglequbitidentity> pro `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="49e0c-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="49e0c-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="49e0c-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="49e0c-111">základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="49e0c-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="49e0c-112">Operátor Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="49e0c-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="49e0c-113">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="49e0c-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="49e0c-114">Qubit, který se má připravit.</span><span class="sxs-lookup"><span data-stu-id="49e0c-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49e0c-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49e0c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="49e0c-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="49e0c-116">Example</span></span>

<span data-ttu-id="49e0c-117">Příprava qubit ve stavu $ \ket{+} $:</span><span class="sxs-lookup"><span data-stu-id="49e0c-117">To prepare a qubit in the $\ket{+}$ state:</span></span>

```qsharp
using (q = Qubit()) {
    PreparePauliEigenstate(PauliX, qubit);
    // ...
}
```