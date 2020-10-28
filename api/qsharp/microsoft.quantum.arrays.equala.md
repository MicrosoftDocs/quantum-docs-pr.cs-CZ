---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equals – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706056"
---
# <a name="equala-function"></a><span data-ttu-id="4b244-102">Equals – funkce</span><span class="sxs-lookup"><span data-stu-id="4b244-102">EqualA function</span></span>

<span data-ttu-id="4b244-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4b244-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4b244-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b244-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b244-105">Zadaná dvě pole stejného typu a predikát, který je definován pro páry prvků pole, kontroluje, zda jsou pole shodná.</span><span class="sxs-lookup"><span data-stu-id="4b244-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="4b244-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4b244-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="4b244-107">EQUAL: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4b244-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4b244-108">Funkce z řazené kolekce členů se `('T, 'T)` `Bool` používá ke kontrole, zda jsou dva prvky pole stejné.</span><span class="sxs-lookup"><span data-stu-id="4b244-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="4b244-109">pole1: t []</span><span class="sxs-lookup"><span data-stu-id="4b244-109">array1 : 'T[]</span></span>

<span data-ttu-id="4b244-110">První pole, které má být porovnáno.</span><span class="sxs-lookup"><span data-stu-id="4b244-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="4b244-111">pole2: t []</span><span class="sxs-lookup"><span data-stu-id="4b244-111">array2 : 'T[]</span></span>

<span data-ttu-id="4b244-112">Druhé pole, které se má porovnat</span><span class="sxs-lookup"><span data-stu-id="4b244-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4b244-113">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4b244-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4b244-114">Hodnota, `true` Pokud a `array1` `array2` jsou rovna.</span><span class="sxs-lookup"><span data-stu-id="4b244-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="4b244-115">To znamená, že pokud mají obě pole stejnou délku, a všechny prvky jsou stejné jako definované pomocí `equal` .</span><span class="sxs-lookup"><span data-stu-id="4b244-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4b244-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4b244-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b244-117">'S</span><span class="sxs-lookup"><span data-stu-id="4b244-117">'T</span></span>

<span data-ttu-id="4b244-118">Typ prvků každého pole.</span><span class="sxs-lookup"><span data-stu-id="4b244-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b244-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4b244-119">Remarks</span></span>

<span data-ttu-id="4b244-120">Tato funkce je definována pro obecné typy. To znamená, že kdykoli máme dvě pole `'T[]` a funkci `equal: ('T, 'T) -> Bool` , tato funkce vrátí `Bool` hodnotu, která označuje, zda jsou pole shodná.</span><span class="sxs-lookup"><span data-stu-id="4b244-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="4b244-121">Pro dvě pole, která mají být považována za EQUAL, musí mít stejnou délku a elementy ve stejné pozici v poli musí být stejné.</span><span class="sxs-lookup"><span data-stu-id="4b244-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>