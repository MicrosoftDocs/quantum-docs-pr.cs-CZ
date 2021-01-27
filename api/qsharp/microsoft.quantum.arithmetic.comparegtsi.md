---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Operace CompareGTSI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: f725bdbaa945a4f87e90fc71930c37642113c21a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846696"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="1155c-102">Operace CompareGTSI</span><span class="sxs-lookup"><span data-stu-id="1155c-102">CompareGTSI operation</span></span>

<span data-ttu-id="1155c-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1155c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1155c-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="1155c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="1155c-105">Obálka pro porovnání se znaménkem pro celé číslo: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="1155c-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1155c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="1155c-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="1155c-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1155c-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="1155c-108">První $n $-bitové číslo</span><span class="sxs-lookup"><span data-stu-id="1155c-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="1155c-109">y: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1155c-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="1155c-110">Druhé $n $-bitové číslo</span><span class="sxs-lookup"><span data-stu-id="1155c-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="1155c-111">výsledek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1155c-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1155c-112">Bude převráceno, pokud $xs > y $</span><span class="sxs-lookup"><span data-stu-id="1155c-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="1155c-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1155c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

