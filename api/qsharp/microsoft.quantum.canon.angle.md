---
uid: Microsoft.Quantum.Canon.Angle
title: Angle – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705521"
---
# <a name="angle-function"></a><span data-ttu-id="45df3-102">Angle – funkce</span><span class="sxs-lookup"><span data-stu-id="45df3-102">Angle function</span></span>

<span data-ttu-id="45df3-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45df3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45df3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45df3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45df3-105">Vrátí hodnotu 1, pokud `index` má lichý počet 1 a-1, pokud `index` má sudý počet 1.</span><span class="sxs-lookup"><span data-stu-id="45df3-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="45df3-106">Popis</span><span class="sxs-lookup"><span data-stu-id="45df3-106">Description</span></span>

<span data-ttu-id="45df3-107">Hodnota odpovídá znaménku součinitele Rademacher-Walshho spektra n-Variable a funkce pro dané přiřazení, které určuje úhel otočení.</span><span class="sxs-lookup"><span data-stu-id="45df3-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="45df3-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="45df3-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="45df3-109">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="45df3-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="45df3-110">Vstupní přiřazení jako celé číslo (od 0 do 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="45df3-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="45df3-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="45df3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

