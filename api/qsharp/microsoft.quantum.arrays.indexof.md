---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221007"
---
# <a name="indexof-function"></a><span data-ttu-id="ae6f4-102">IndexOf – funkce</span><span class="sxs-lookup"><span data-stu-id="ae6f4-102">IndexOf function</span></span>

<span data-ttu-id="ae6f4-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ae6f4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ae6f4-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae6f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae6f4-105">Vrátí první index prvního prvku v poli, který splňuje daný predikát.</span><span class="sxs-lookup"><span data-stu-id="ae6f4-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="ae6f4-106">Pokud žádný takový prvek neexistuje, vrátí hodnotu-1.</span><span class="sxs-lookup"><span data-stu-id="ae6f4-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="ae6f4-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="ae6f4-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ae6f4-108">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ae6f4-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ae6f4-109">Funkce predikátu, která funguje na prvcích pole.</span><span class="sxs-lookup"><span data-stu-id="ae6f4-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="ae6f4-110">Šipka: t []</span><span class="sxs-lookup"><span data-stu-id="ae6f4-110">arr : 'T[]</span></span>

<span data-ttu-id="ae6f4-111">Pole, které má být prohledáno pomocí daného predikátu.</span><span class="sxs-lookup"><span data-stu-id="ae6f4-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="ae6f4-112">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae6f4-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae6f4-113">Buď nejmenší index, `idx` který `predicate(arr[idx])` je true, nebo-1, pokud žádný takový prvek neexistuje.</span><span class="sxs-lookup"><span data-stu-id="ae6f4-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ae6f4-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ae6f4-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ae6f4-115">'S</span><span class="sxs-lookup"><span data-stu-id="ae6f4-115">'T</span></span>

