---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operace dělení
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223302"
---
# <a name="dividei-operation"></a><span data-ttu-id="0f22c-102">Operace dělení</span><span class="sxs-lookup"><span data-stu-id="0f22c-102">DivideI operation</span></span>

<span data-ttu-id="0f22c-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0f22c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0f22c-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="0f22c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="0f22c-105">Vydělí dvě celá čísla.</span><span class="sxs-lookup"><span data-stu-id="0f22c-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0f22c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="0f22c-106">Description</span></span>

<span data-ttu-id="0f22c-107">`xs` bude obsahovat zbytek `xs - floor(xs/ys) * ys` a `result` bude obsahovat `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="0f22c-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="0f22c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="0f22c-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0f22c-109">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f22c-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f22c-110">$n $-bit děleno, bude zbytek nahrazen.</span><span class="sxs-lookup"><span data-stu-id="0f22c-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0f22c-111">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f22c-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f22c-112">$n $-bitový dělitel</span><span class="sxs-lookup"><span data-stu-id="0f22c-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="0f22c-113">výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f22c-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f22c-114">$n bitový výsledek, musí být ve stavu $ \ket {0} $ zpočátku a bude nahrazen výsledkem dělení celého čísla.</span><span class="sxs-lookup"><span data-stu-id="0f22c-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f22c-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f22c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0f22c-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0f22c-116">Remarks</span></span>

<span data-ttu-id="0f22c-117">K implementaci dělení používá standardní přístup SHIFT a odečíst.</span><span class="sxs-lookup"><span data-stu-id="0f22c-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="0f22c-118">Řízená verze je specializovaná, taková odčítání nevyžaduje další ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="0f22c-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>