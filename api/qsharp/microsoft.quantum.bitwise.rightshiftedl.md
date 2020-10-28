---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705577"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="f7a79-102">RightShiftedL – funkce</span><span class="sxs-lookup"><span data-stu-id="f7a79-102">RightShiftedL function</span></span>

<span data-ttu-id="f7a79-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="f7a79-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="f7a79-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7a79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7a79-105">Posune bitovou reprezentaci čísla přímo podle zadaného počtu bitů.</span><span class="sxs-lookup"><span data-stu-id="f7a79-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="f7a79-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f7a79-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="f7a79-107">hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f7a79-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f7a79-108">Číslo, jehož bitová reprezentace má být posunuta doprava (méně významná).</span><span class="sxs-lookup"><span data-stu-id="f7a79-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="f7a79-109">částka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7a79-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7a79-110">Počet bitů, které `value` mají být posunuty doprava.</span><span class="sxs-lookup"><span data-stu-id="f7a79-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="f7a79-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f7a79-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f7a79-112">Hodnota, která `value` se posouvá doprava po `amount` bitech.</span><span class="sxs-lookup"><span data-stu-id="f7a79-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7a79-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f7a79-113">Remarks</span></span>

<span data-ttu-id="f7a79-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="f7a79-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```