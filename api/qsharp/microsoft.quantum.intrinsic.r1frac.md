---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: Operace R1Frac
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfae01d11524f64ceebd53aa8544d7ea48c40f31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818691"
---
# <a name="r1frac-operation"></a><span data-ttu-id="cde7d-102">Operace R1Frac</span><span class="sxs-lookup"><span data-stu-id="cde7d-102">R1Frac operation</span></span>

<span data-ttu-id="cde7d-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cde7d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cde7d-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cde7d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cde7d-105">Použije rotaci o stavu $ \ket {1} $ podle úhlu zadaného jako zlomek dyadic.</span><span class="sxs-lookup"><span data-stu-id="cde7d-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="cde7d-106">\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \pi k/2 ^ n}).</span><span class="sxs-lookup"><span data-stu-id="cde7d-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="cde7d-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="cde7d-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="cde7d-108">Tato operace používá **opačnou** konvenci znaménka z @"microsoft.quantum.intrinsic.r" a nezahrnuje faktor $1/2 $ zahrnutý do @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="cde7d-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cde7d-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="cde7d-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="cde7d-110">Čitatel: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cde7d-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cde7d-111">Čitatel v dyadic zlomkové reprezentace úhlu, o kterou má být qubit otočen.</span><span class="sxs-lookup"><span data-stu-id="cde7d-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="cde7d-112">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cde7d-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cde7d-113">Mocnina dvou určující jmenovatele úhlu, podle kterého má být qubit otočen.</span><span class="sxs-lookup"><span data-stu-id="cde7d-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="cde7d-114">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cde7d-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cde7d-115">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="cde7d-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cde7d-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cde7d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cde7d-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cde7d-117">Remarks</span></span>

<span data-ttu-id="cde7d-118">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="cde7d-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```