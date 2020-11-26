---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219664"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="e4a9f-102">LeftShiftedL – funkce</span><span class="sxs-lookup"><span data-stu-id="e4a9f-102">LeftShiftedL function</span></span>

<span data-ttu-id="e4a9f-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="e4a9f-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="e4a9f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4a9f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4a9f-105">Posune bitovou reprezentaci čísla vlevo o daný počet bitů.</span><span class="sxs-lookup"><span data-stu-id="e4a9f-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="e4a9f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e4a9f-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="e4a9f-107">hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e4a9f-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e4a9f-108">Číslo, jehož bitová reprezentace má být posunuta doleva (důležitější).</span><span class="sxs-lookup"><span data-stu-id="e4a9f-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="e4a9f-109">částka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4a9f-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4a9f-110">Počet bitů, které `value` mají být posunuty doleva.</span><span class="sxs-lookup"><span data-stu-id="e4a9f-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="e4a9f-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e4a9f-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e4a9f-112">Hodnota, která `value` se posouvá vlevo od `amount` bitů.</span><span class="sxs-lookup"><span data-stu-id="e4a9f-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4a9f-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e4a9f-113">Remarks</span></span>

<span data-ttu-id="e4a9f-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="e4a9f-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```