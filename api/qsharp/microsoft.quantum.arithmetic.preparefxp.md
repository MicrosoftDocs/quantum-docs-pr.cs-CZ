---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: Operace PrepareFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 29ba66700db83d0786a70841c7b03843a9ae6219
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222401"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="66614-102">Operace PrepareFxP</span><span class="sxs-lookup"><span data-stu-id="66614-102">PrepareFxP operation</span></span>

<span data-ttu-id="66614-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="66614-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="66614-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="66614-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="66614-105">Inicializovat číslo s pevnou desetinnou čárkou pro klasický konstantu.</span><span class="sxs-lookup"><span data-stu-id="66614-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="66614-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="66614-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="66614-107">Konstanta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="66614-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="66614-108">Konstanta, na kterou se má inicializovat číslo s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="66614-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="66614-109">FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="66614-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="66614-110">Číslo s pevnou desetinnou čárkou (typu FixedPoint) pro inicializaci.</span><span class="sxs-lookup"><span data-stu-id="66614-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66614-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66614-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

