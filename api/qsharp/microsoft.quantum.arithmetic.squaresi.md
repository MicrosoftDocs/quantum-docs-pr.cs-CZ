---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Operace čtverců
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842928"
---
# <a name="squaresi-operation"></a><span data-ttu-id="85610-102">Operace čtverců</span><span class="sxs-lookup"><span data-stu-id="85610-102">SquareSI operation</span></span>

<span data-ttu-id="85610-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="85610-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="85610-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="85610-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="85610-105">Čtvercové celé číslo se znaménkem `xs` a uložení výsledku v `result` , které musí být zpočátku nula.</span><span class="sxs-lookup"><span data-stu-id="85610-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="85610-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="85610-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="85610-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="85610-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="85610-108">n-bit celé číslo na čtverec (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="85610-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="85610-109">výsledek: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="85610-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="85610-110">2N výsledek (SignedLittleEndian), musí být ve stavu $ \ket {0} $ zpočátku.</span><span class="sxs-lookup"><span data-stu-id="85610-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="85610-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85610-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="85610-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="85610-112">Remarks</span></span>

<span data-ttu-id="85610-113">Implementace spoléhá na IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="85610-113">The implementation relies on IntegerSquare.</span></span>