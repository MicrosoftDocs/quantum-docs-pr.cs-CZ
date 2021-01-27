---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842139"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="ee62b-102">LeftShiftedL – funkce</span><span class="sxs-lookup"><span data-stu-id="ee62b-102">LeftShiftedL function</span></span>

<span data-ttu-id="ee62b-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="ee62b-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="ee62b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee62b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee62b-105">Posune bitovou reprezentaci čísla vlevo o daný počet bitů.</span><span class="sxs-lookup"><span data-stu-id="ee62b-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="ee62b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ee62b-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="ee62b-107">hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ee62b-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ee62b-108">Číslo, jehož bitová reprezentace má být posunuta doleva (důležitější).</span><span class="sxs-lookup"><span data-stu-id="ee62b-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="ee62b-109">částka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee62b-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee62b-110">Počet bitů, které `value` mají být posunuty doleva.</span><span class="sxs-lookup"><span data-stu-id="ee62b-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="ee62b-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ee62b-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ee62b-112">Hodnota, která `value` se posouvá vlevo od `amount` bitů.</span><span class="sxs-lookup"><span data-stu-id="ee62b-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee62b-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ee62b-113">Remarks</span></span>

<span data-ttu-id="ee62b-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="ee62b-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```