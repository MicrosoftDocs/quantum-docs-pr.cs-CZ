---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operace čtverečních
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221857"
---
# <a name="squarei-operation"></a><span data-ttu-id="0418d-102">Operace čtverečních</span><span class="sxs-lookup"><span data-stu-id="0418d-102">SquareI operation</span></span>

<span data-ttu-id="0418d-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0418d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0418d-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="0418d-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="0418d-105">Vypočítá čtverci celého čísla `xs` do `result` , které musí být zpočátku nula.</span><span class="sxs-lookup"><span data-stu-id="0418d-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0418d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0418d-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0418d-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0418d-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0418d-108">$n $-bitové číslo do čtverce (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0418d-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="0418d-109">výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0418d-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0418d-110">$2N $-bit výsledek (LittleEndian), musí být ve stavu $ \ket {0} $ zpočátku.</span><span class="sxs-lookup"><span data-stu-id="0418d-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0418d-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0418d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0418d-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0418d-112">Remarks</span></span>

<span data-ttu-id="0418d-113">K výpočtu čtverce používá standardní přístup Shift-and-Add.</span><span class="sxs-lookup"><span data-stu-id="0418d-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="0418d-114">Uloží $n-$1 qubits ve srovnání s řešením přímého přeposílání, které před použitím regulárního násobitele nejdřív zkopíruje XS a potom operaci kopírování vrátí zpět.</span><span class="sxs-lookup"><span data-stu-id="0418d-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>