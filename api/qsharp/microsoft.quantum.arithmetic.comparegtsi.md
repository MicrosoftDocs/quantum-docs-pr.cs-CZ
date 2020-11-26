---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Operace CompareGTSI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: a0e8ef66f1e1a62d4f6a78364135376810507534
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223489"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="714bf-102">Operace CompareGTSI</span><span class="sxs-lookup"><span data-stu-id="714bf-102">CompareGTSI operation</span></span>

<span data-ttu-id="714bf-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="714bf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="714bf-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="714bf-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="714bf-105">Obálka pro porovnání se znaménkem pro celé číslo: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="714bf-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="714bf-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="714bf-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="714bf-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="714bf-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="714bf-108">První $n $-bitové číslo</span><span class="sxs-lookup"><span data-stu-id="714bf-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="714bf-109">y: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="714bf-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="714bf-110">Druhé $n $-bitové číslo</span><span class="sxs-lookup"><span data-stu-id="714bf-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="714bf-111">výsledek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="714bf-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="714bf-112">Bude převráceno, pokud $xs > y $</span><span class="sxs-lookup"><span data-stu-id="714bf-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="714bf-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="714bf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

