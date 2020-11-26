---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Operace čtverců
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7fe4d27b974a06b019a2b15710fbc51b598027b4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221823"
---
# <a name="squaresi-operation"></a><span data-ttu-id="e1e6f-102">Operace čtverců</span><span class="sxs-lookup"><span data-stu-id="e1e6f-102">SquareSI operation</span></span>

<span data-ttu-id="e1e6f-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e1e6f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e1e6f-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="e1e6f-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="e1e6f-105">Čtvercové celé číslo se znaménkem `xs` a uložení výsledku v `result` , které musí být zpočátku nula.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e1e6f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e1e6f-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="e1e6f-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1e6f-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="e1e6f-108">n-bit celé číslo na čtverec (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1e6f-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="e1e6f-109">výsledek: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1e6f-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="e1e6f-110">2N výsledek (SignedLittleEndian), musí být ve stavu $ \ket {0} $ zpočátku.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1e6f-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1e6f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e1e6f-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e1e6f-112">Remarks</span></span>

<span data-ttu-id="e1e6f-113">Implementace spoléhá na IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-113">The implementation relies on IntegerSquare.</span></span>