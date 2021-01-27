---
uid: Microsoft.Quantum.Canon.Angle
title: Angle – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842042"
---
# <a name="angle-function"></a><span data-ttu-id="57ebe-102">Angle – funkce</span><span class="sxs-lookup"><span data-stu-id="57ebe-102">Angle function</span></span>

<span data-ttu-id="57ebe-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57ebe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57ebe-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57ebe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57ebe-105">Vrátí hodnotu 1, pokud `index` má lichý počet 1 a-1, pokud `index` má sudý počet 1.</span><span class="sxs-lookup"><span data-stu-id="57ebe-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="57ebe-106">Popis</span><span class="sxs-lookup"><span data-stu-id="57ebe-106">Description</span></span>

<span data-ttu-id="57ebe-107">Hodnota odpovídá znaménku součinitele Rademacher-Walshho spektra n-Variable a funkce pro dané přiřazení, které určuje úhel otočení.</span><span class="sxs-lookup"><span data-stu-id="57ebe-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="57ebe-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="57ebe-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="57ebe-109">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57ebe-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57ebe-110">Vstupní přiřazení jako celé číslo (od 0 do 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="57ebe-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="57ebe-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57ebe-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

