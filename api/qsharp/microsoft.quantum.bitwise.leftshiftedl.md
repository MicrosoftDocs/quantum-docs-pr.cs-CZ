---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705617"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="fe13a-102">LeftShiftedL – funkce</span><span class="sxs-lookup"><span data-stu-id="fe13a-102">LeftShiftedL function</span></span>

<span data-ttu-id="fe13a-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="fe13a-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="fe13a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe13a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe13a-105">Posune bitovou reprezentaci čísla vlevo o daný počet bitů.</span><span class="sxs-lookup"><span data-stu-id="fe13a-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="fe13a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fe13a-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="fe13a-107">hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe13a-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fe13a-108">Číslo, jehož bitová reprezentace má být posunuta doleva (důležitější).</span><span class="sxs-lookup"><span data-stu-id="fe13a-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="fe13a-109">částka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fe13a-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fe13a-110">Počet bitů, které `value` mají být posunuty doleva.</span><span class="sxs-lookup"><span data-stu-id="fe13a-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="fe13a-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe13a-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fe13a-112">Hodnota, která `value` se posouvá vlevo od `amount` bitů.</span><span class="sxs-lookup"><span data-stu-id="fe13a-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe13a-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fe13a-113">Remarks</span></span>

<span data-ttu-id="fe13a-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="fe13a-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```