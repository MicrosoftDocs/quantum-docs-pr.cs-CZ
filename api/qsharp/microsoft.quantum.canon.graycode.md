---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704168"
---
# <a name="graycode-function"></a><span data-ttu-id="9cfee-102">GrayCode – funkce</span><span class="sxs-lookup"><span data-stu-id="9cfee-102">GrayCode function</span></span>

<span data-ttu-id="9cfee-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9cfee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9cfee-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9cfee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9cfee-105">Vytvoří šedé sekvence kódu.</span><span class="sxs-lookup"><span data-stu-id="9cfee-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="9cfee-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9cfee-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="9cfee-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9cfee-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9cfee-108">Počet bitů</span><span class="sxs-lookup"><span data-stu-id="9cfee-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="9cfee-109">Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="9cfee-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="9cfee-110">Pole řazených kolekcí členů.</span><span class="sxs-lookup"><span data-stu-id="9cfee-110">Array of tuples.</span></span> <span data-ttu-id="9cfee-111">První hodnota v řazené kolekci členů je hodnota v GrayCode pořadí sekundová hodnota v řazené kolekci členů je pozice pro změnu v aktuální hodnotě, která se získá jako další.</span><span class="sxs-lookup"><span data-stu-id="9cfee-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>