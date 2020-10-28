---
uid: Microsoft.Quantum.Intrinsic.H
title: H operace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: H
qsharp.summary: >-
  Applies the Hadamard transformation to a single qubit.

  \begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 1ba99d2f34c601b46b82fb853008464c3add965d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697721"
---
# <a name="h-operation"></a><span data-ttu-id="40b28-102">H operace</span><span class="sxs-lookup"><span data-stu-id="40b28-102">H operation</span></span>

<span data-ttu-id="40b28-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="40b28-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="40b28-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="40b28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="40b28-105">Aplikuje transformaci Hadamard na jeden qubit.</span><span class="sxs-lookup"><span data-stu-id="40b28-105">Applies the Hadamard transformation to a single qubit.</span></span>

<span data-ttu-id="40b28-106">\begin{align} H \mathrel{: =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="40b28-106">\begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="40b28-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="40b28-107">\end{align}</span></span>

```qsharp
operation H (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="40b28-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="40b28-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="40b28-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="40b28-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="40b28-110">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="40b28-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40b28-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40b28-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

