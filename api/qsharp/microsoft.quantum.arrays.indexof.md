---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848526"
---
# <a name="indexof-function"></a><span data-ttu-id="8f936-102">IndexOf – funkce</span><span class="sxs-lookup"><span data-stu-id="8f936-102">IndexOf function</span></span>

<span data-ttu-id="8f936-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8f936-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8f936-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f936-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f936-105">Vrátí první index prvního prvku v poli, který splňuje daný predikát.</span><span class="sxs-lookup"><span data-stu-id="8f936-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="8f936-106">Pokud žádný takový prvek neexistuje, vrátí hodnotu-1.</span><span class="sxs-lookup"><span data-stu-id="8f936-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="8f936-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="8f936-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="8f936-108">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8f936-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8f936-109">Funkce predikátu, která funguje na prvcích pole.</span><span class="sxs-lookup"><span data-stu-id="8f936-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="8f936-110">Šipka: t []</span><span class="sxs-lookup"><span data-stu-id="8f936-110">arr : 'T[]</span></span>

<span data-ttu-id="8f936-111">Pole, které má být prohledáno pomocí daného predikátu.</span><span class="sxs-lookup"><span data-stu-id="8f936-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="8f936-112">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8f936-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8f936-113">Buď nejmenší index, `idx` který `predicate(arr[idx])` je true, nebo-1, pokud žádný takový prvek neexistuje.</span><span class="sxs-lookup"><span data-stu-id="8f936-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8f936-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8f936-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f936-115">'S</span><span class="sxs-lookup"><span data-stu-id="8f936-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="8f936-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="8f936-116">Example</span></span>

<span data-ttu-id="8f936-117">Předpokládejme, že `IsEven : Int -> Bool` se jedná o funkci, která vrací `true` pouze v případě, že je její vstup i.</span><span class="sxs-lookup"><span data-stu-id="8f936-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="8f936-118">Pak lze použít s `IndexOf` k nalezení prvního i elementu v poli:</span><span class="sxs-lookup"><span data-stu-id="8f936-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```