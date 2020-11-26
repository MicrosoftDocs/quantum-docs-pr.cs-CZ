---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: Operace CompareGTI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223472"
---
# <a name="comparegti-operation"></a><span data-ttu-id="c392c-102">Operace CompareGTI</span><span class="sxs-lookup"><span data-stu-id="c392c-102">CompareGTI operation</span></span>

<span data-ttu-id="c392c-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c392c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c392c-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c392c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c392c-105">Obálka pro porovnání celého čísla: `result = x > y` .</span><span class="sxs-lookup"><span data-stu-id="c392c-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c392c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c392c-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c392c-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c392c-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c392c-108">První $n $-bitové číslo</span><span class="sxs-lookup"><span data-stu-id="c392c-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c392c-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c392c-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c392c-110">Druhé $n $-bitové číslo</span><span class="sxs-lookup"><span data-stu-id="c392c-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="c392c-111">výsledek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c392c-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c392c-112">Bude převráceno, pokud $x > y $</span><span class="sxs-lookup"><span data-stu-id="c392c-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="c392c-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c392c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

