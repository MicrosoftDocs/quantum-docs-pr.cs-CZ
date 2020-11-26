---
uid: Microsoft.Quantum.Canon.RAll1
title: Operace RAll1
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 36e460f93b4349bc2e3da9bfb22cb0aa82ef1795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205524"
---
# <a name="rall1-operation"></a><span data-ttu-id="589b9-102">Operace RAll1</span><span class="sxs-lookup"><span data-stu-id="589b9-102">RAll1 operation</span></span>

<span data-ttu-id="589b9-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="589b9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="589b9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="589b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="589b9-105">Provede operaci posunutí fáze.</span><span class="sxs-lookup"><span data-stu-id="589b9-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="589b9-106">$R = \boldone-(1-e ^ {i \phi}) \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="589b9-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="589b9-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="589b9-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="589b9-108">fáze: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="589b9-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="589b9-109">Fáze $ \phi $ se aplikuje na stav $ \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="589b9-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="589b9-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="589b9-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="589b9-111">Registr, jehož stav má být otočen pomocí $R $.</span><span class="sxs-lookup"><span data-stu-id="589b9-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="589b9-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="589b9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

