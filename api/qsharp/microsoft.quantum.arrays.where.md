---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842220"
---
# <a name="where-function"></a><span data-ttu-id="ccb91-102">WHERE – funkce</span><span class="sxs-lookup"><span data-stu-id="ccb91-102">Where function</span></span>

<span data-ttu-id="ccb91-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ccb91-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ccb91-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ccb91-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ccb91-105">V případě predikátu a pole vrátí indexy tohoto pole, kde má predikát hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="ccb91-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="ccb91-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ccb91-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ccb91-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ccb91-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ccb91-108">Funkce z `'T` na logickou hodnotu, která slouží k filtrování prvků.</span><span class="sxs-lookup"><span data-stu-id="ccb91-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="ccb91-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="ccb91-109">array : 'T[]</span></span>

<span data-ttu-id="ccb91-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="ccb91-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="ccb91-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ccb91-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ccb91-112">Pole indexů, kde `predicate` je true.</span><span class="sxs-lookup"><span data-stu-id="ccb91-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ccb91-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ccb91-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ccb91-114">'S</span><span class="sxs-lookup"><span data-stu-id="ccb91-114">'T</span></span>

<span data-ttu-id="ccb91-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="ccb91-115">The type of `array` elements.</span></span>