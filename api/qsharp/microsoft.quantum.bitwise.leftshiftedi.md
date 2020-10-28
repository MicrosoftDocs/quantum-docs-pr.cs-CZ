---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705640"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="19698-102">LeftShiftedI – funkce</span><span class="sxs-lookup"><span data-stu-id="19698-102">LeftShiftedI function</span></span>

<span data-ttu-id="19698-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="19698-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="19698-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19698-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19698-105">Posune bitovou reprezentaci čísla vlevo o daný počet bitů.</span><span class="sxs-lookup"><span data-stu-id="19698-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="19698-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="19698-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="19698-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19698-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19698-108">Číslo, jehož bitová reprezentace má být posunuta doleva (důležitější).</span><span class="sxs-lookup"><span data-stu-id="19698-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="19698-109">částka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19698-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19698-110">Počet bitů, které `value` mají být posunuty doleva.</span><span class="sxs-lookup"><span data-stu-id="19698-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="19698-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19698-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19698-112">Hodnota, která `value` se posouvá vlevo od `amount` bitů.</span><span class="sxs-lookup"><span data-stu-id="19698-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="19698-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="19698-113">Remarks</span></span>

<span data-ttu-id="19698-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="19698-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```