---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705584"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="2a281-102">RightShiftedI – funkce</span><span class="sxs-lookup"><span data-stu-id="2a281-102">RightShiftedI function</span></span>

<span data-ttu-id="2a281-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="2a281-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="2a281-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a281-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a281-105">Posune bitovou reprezentaci čísla přímo podle zadaného počtu bitů.</span><span class="sxs-lookup"><span data-stu-id="2a281-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="2a281-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2a281-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="2a281-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a281-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a281-108">Číslo, jehož bitová reprezentace má být posunuta doprava (méně významná).</span><span class="sxs-lookup"><span data-stu-id="2a281-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="2a281-109">částka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a281-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a281-110">Počet bitů, které `value` mají být posunuty doprava.</span><span class="sxs-lookup"><span data-stu-id="2a281-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="2a281-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a281-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a281-112">Hodnota, která `value` se posouvá doprava po `amount` bitech.</span><span class="sxs-lookup"><span data-stu-id="2a281-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a281-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2a281-113">Remarks</span></span>

<span data-ttu-id="2a281-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="2a281-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```