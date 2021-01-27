---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845312"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="95442-102">LeftShiftedI – funkce</span><span class="sxs-lookup"><span data-stu-id="95442-102">LeftShiftedI function</span></span>

<span data-ttu-id="95442-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="95442-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="95442-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95442-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95442-105">Posune bitovou reprezentaci čísla vlevo o daný počet bitů.</span><span class="sxs-lookup"><span data-stu-id="95442-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="95442-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="95442-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="95442-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95442-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95442-108">Číslo, jehož bitová reprezentace má být posunuta doleva (důležitější).</span><span class="sxs-lookup"><span data-stu-id="95442-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="95442-109">částka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95442-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95442-110">Počet bitů, které `value` mají být posunuty doleva.</span><span class="sxs-lookup"><span data-stu-id="95442-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="95442-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95442-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95442-112">Hodnota, která `value` se posouvá vlevo od `amount` bitů.</span><span class="sxs-lookup"><span data-stu-id="95442-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="95442-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="95442-113">Remarks</span></span>

<span data-ttu-id="95442-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="95442-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```