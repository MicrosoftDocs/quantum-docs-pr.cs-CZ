---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206880"
---
# <a name="graycode-function"></a><span data-ttu-id="4bef7-102">GrayCode – funkce</span><span class="sxs-lookup"><span data-stu-id="4bef7-102">GrayCode function</span></span>

<span data-ttu-id="4bef7-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4bef7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4bef7-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4bef7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4bef7-105">Vytvoří šedé sekvence kódu.</span><span class="sxs-lookup"><span data-stu-id="4bef7-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="4bef7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4bef7-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="4bef7-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4bef7-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4bef7-108">Počet bitů</span><span class="sxs-lookup"><span data-stu-id="4bef7-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="4bef7-109">Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="4bef7-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="4bef7-110">Pole řazených kolekcí členů.</span><span class="sxs-lookup"><span data-stu-id="4bef7-110">Array of tuples.</span></span> <span data-ttu-id="4bef7-111">První hodnota v řazené kolekci členů je hodnota v GrayCode pořadí sekundová hodnota v řazené kolekci členů je pozice pro změnu v aktuální hodnotě, která se získá jako další.</span><span class="sxs-lookup"><span data-stu-id="4bef7-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>