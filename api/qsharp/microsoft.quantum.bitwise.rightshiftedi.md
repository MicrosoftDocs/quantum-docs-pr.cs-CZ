---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845259"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="538dc-102">RightShiftedI – funkce</span><span class="sxs-lookup"><span data-stu-id="538dc-102">RightShiftedI function</span></span>

<span data-ttu-id="538dc-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="538dc-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="538dc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="538dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="538dc-105">Posune bitovou reprezentaci čísla přímo podle zadaného počtu bitů.</span><span class="sxs-lookup"><span data-stu-id="538dc-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="538dc-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="538dc-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="538dc-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="538dc-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="538dc-108">Číslo, jehož bitová reprezentace má být posunuta doprava (méně významná).</span><span class="sxs-lookup"><span data-stu-id="538dc-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="538dc-109">částka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="538dc-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="538dc-110">Počet bitů, které `value` mají být posunuty doprava.</span><span class="sxs-lookup"><span data-stu-id="538dc-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="538dc-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="538dc-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="538dc-112">Hodnota, která `value` se posouvá doprava po `amount` bitech.</span><span class="sxs-lookup"><span data-stu-id="538dc-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="538dc-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="538dc-113">Remarks</span></span>

<span data-ttu-id="538dc-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="538dc-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```