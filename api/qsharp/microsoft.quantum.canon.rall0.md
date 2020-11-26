---
uid: Microsoft.Quantum.Canon.RAll0
title: Operace RAll0
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: bd1f796209a15f290315e55b872ae3b3e508a68b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205656"
---
# <a name="rall0-operation"></a><span data-ttu-id="40354-102">Operace RAll0</span><span class="sxs-lookup"><span data-stu-id="40354-102">RAll0 operation</span></span>

<span data-ttu-id="40354-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="40354-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="40354-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40354-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40354-105">Provede operaci posunutí fáze.</span><span class="sxs-lookup"><span data-stu-id="40354-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="40354-106">$R = \boldone-(1-e ^ {i \phi}) \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="40354-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="40354-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="40354-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="40354-108">fáze: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="40354-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="40354-109">Fáze $ \phi $ se aplikuje na stav $ \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="40354-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="40354-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="40354-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="40354-111">Registr, jehož stav má být otočen pomocí $R $.</span><span class="sxs-lookup"><span data-stu-id="40354-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40354-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40354-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="40354-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="40354-113">See Also</span></span>

- [<span data-ttu-id="40354-114">Microsoft. proRAll1. Canon.</span><span class="sxs-lookup"><span data-stu-id="40354-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)