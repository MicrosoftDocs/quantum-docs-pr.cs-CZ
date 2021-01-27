---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842099"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="eebc6-102">RightShiftedL – funkce</span><span class="sxs-lookup"><span data-stu-id="eebc6-102">RightShiftedL function</span></span>

<span data-ttu-id="eebc6-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="eebc6-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="eebc6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eebc6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eebc6-105">Posune bitovou reprezentaci čísla přímo podle zadaného počtu bitů.</span><span class="sxs-lookup"><span data-stu-id="eebc6-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="eebc6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="eebc6-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="eebc6-107">hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eebc6-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eebc6-108">Číslo, jehož bitová reprezentace má být posunuta doprava (méně významná).</span><span class="sxs-lookup"><span data-stu-id="eebc6-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="eebc6-109">částka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eebc6-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eebc6-110">Počet bitů, které `value` mají být posunuty doprava.</span><span class="sxs-lookup"><span data-stu-id="eebc6-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="eebc6-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eebc6-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eebc6-112">Hodnota, která `value` se posouvá doprava po `amount` bitech.</span><span class="sxs-lookup"><span data-stu-id="eebc6-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="eebc6-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="eebc6-113">Remarks</span></span>

<span data-ttu-id="eebc6-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="eebc6-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```