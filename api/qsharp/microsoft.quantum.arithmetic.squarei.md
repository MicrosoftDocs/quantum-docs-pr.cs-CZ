---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operace čtverečních
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706224"
---
# <a name="squarei-operation"></a><span data-ttu-id="184eb-102">Operace čtverečních</span><span class="sxs-lookup"><span data-stu-id="184eb-102">SquareI operation</span></span>

<span data-ttu-id="184eb-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="184eb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="184eb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="184eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="184eb-105">Vypočítá čtverci celého čísla `xs` do `result` , které musí být zpočátku nula.</span><span class="sxs-lookup"><span data-stu-id="184eb-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="184eb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="184eb-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="184eb-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="184eb-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="184eb-108">$n $-bitové číslo do čtverce (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="184eb-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="184eb-109">výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="184eb-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="184eb-110">$2N $-bit výsledek (LittleEndian), musí být ve stavu $ \ket {0} $ zpočátku.</span><span class="sxs-lookup"><span data-stu-id="184eb-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="184eb-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="184eb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="184eb-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="184eb-112">Remarks</span></span>

<span data-ttu-id="184eb-113">K výpočtu čtverce používá standardní přístup Shift-and-Add.</span><span class="sxs-lookup"><span data-stu-id="184eb-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="184eb-114">Uloží $n-$1 qubits ve srovnání s řešením přímého přeposílání, které před použitím regulárního násobitele nejdřív zkopíruje XS a potom operaci kopírování vrátí zpět.</span><span class="sxs-lookup"><span data-stu-id="184eb-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>