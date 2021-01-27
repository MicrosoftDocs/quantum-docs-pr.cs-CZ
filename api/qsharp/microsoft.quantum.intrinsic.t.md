---
uid: Microsoft.Quantum.Intrinsic.T
title: T – operace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: bee252d9905aed26f6bf663f895e464e38073f44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817513"
---
# <a name="t-operation"></a><span data-ttu-id="7b852-102">T – operace</span><span class="sxs-lookup"><span data-stu-id="7b852-102">T operation</span></span>

<span data-ttu-id="7b852-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7b852-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7b852-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7b852-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7b852-105">Aplikuje bránu T na jeden qubit.</span><span class="sxs-lookup"><span data-stu-id="7b852-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7b852-106">Popis</span><span class="sxs-lookup"><span data-stu-id="7b852-106">Description</span></span>

<span data-ttu-id="7b852-107">Tato operace může být simulována jednotnou maticí \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="7b852-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="7b852-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="7b852-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="7b852-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="7b852-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="7b852-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7b852-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7b852-111">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="7b852-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7b852-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b852-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

