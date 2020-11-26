---
uid: Microsoft.Quantum.Intrinsic.S
title: Operace S
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: c697408c4efe1963787b5aee8f0d3bb6b9e64dd5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198448"
---
# <a name="s-operation"></a><span data-ttu-id="9131e-102">Operace S</span><span class="sxs-lookup"><span data-stu-id="9131e-102">S operation</span></span>

<span data-ttu-id="9131e-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="9131e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="9131e-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9131e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9131e-105">Aplikuje bránu S na jeden qubit.</span><span class="sxs-lookup"><span data-stu-id="9131e-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9131e-106">Popis</span><span class="sxs-lookup"><span data-stu-id="9131e-106">Description</span></span>

<span data-ttu-id="9131e-107">Tuto operaci může simulovat jednotná matice \begin{align} S \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="9131e-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="9131e-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="9131e-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="9131e-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="9131e-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="9131e-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9131e-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9131e-111">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="9131e-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9131e-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9131e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

