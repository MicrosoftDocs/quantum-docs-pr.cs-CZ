---
uid: Microsoft.Quantum.Canon.HY
title: Operace HY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: 119d78c4cd8d5e5d92cb54ff652b082a1b99ae06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840450"
---
# <a name="hy-operation"></a><span data-ttu-id="2d039-102">Operace HY</span><span class="sxs-lookup"><span data-stu-id="2d039-102">HY operation</span></span>

<span data-ttu-id="2d039-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2d039-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2d039-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d039-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d039-105">Aplikuje na transformaci Hadamard, která přemění osy Z a Y, na bázi Y.</span><span class="sxs-lookup"><span data-stu-id="2d039-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="2d039-106">Transformace Y Hadamard $H _Y = S H $ v jednom qubit je:</span><span class="sxs-lookup"><span data-stu-id="2d039-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="2d039-107">\begin{align} H_Y \mathrel{: =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2d039-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="2d039-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2d039-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2d039-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="2d039-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="2d039-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2d039-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2d039-111">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="2d039-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d039-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d039-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2d039-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="2d039-113">See Also</span></span>

- [<span data-ttu-id="2d039-114">Microsoft. pro, vnitřní. H</span><span class="sxs-lookup"><span data-stu-id="2d039-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)