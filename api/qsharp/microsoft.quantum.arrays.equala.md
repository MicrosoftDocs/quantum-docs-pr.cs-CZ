---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equals – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848694"
---
# <a name="equala-function"></a><span data-ttu-id="fd9a1-102">Equals – funkce</span><span class="sxs-lookup"><span data-stu-id="fd9a1-102">EqualA function</span></span>

<span data-ttu-id="fd9a1-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fd9a1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fd9a1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd9a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd9a1-105">Zadaná dvě pole stejného typu a predikát, který je definován pro páry prvků pole, kontroluje, zda jsou pole shodná.</span><span class="sxs-lookup"><span data-stu-id="fd9a1-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="fd9a1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fd9a1-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="fd9a1-107">EQUAL: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fd9a1-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fd9a1-108">Funkce z řazené kolekce členů se `('T, 'T)` `Bool` používá ke kontrole, zda jsou dva prvky pole stejné.</span><span class="sxs-lookup"><span data-stu-id="fd9a1-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="fd9a1-109">pole1: t []</span><span class="sxs-lookup"><span data-stu-id="fd9a1-109">array1 : 'T[]</span></span>

<span data-ttu-id="fd9a1-110">První pole, které má být porovnáno.</span><span class="sxs-lookup"><span data-stu-id="fd9a1-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="fd9a1-111">pole2: t []</span><span class="sxs-lookup"><span data-stu-id="fd9a1-111">array2 : 'T[]</span></span>

<span data-ttu-id="fd9a1-112">Druhé pole, které se má porovnat</span><span class="sxs-lookup"><span data-stu-id="fd9a1-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fd9a1-113">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fd9a1-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fd9a1-114">Hodnota, `true` Pokud a `array1` `array2` jsou rovna.</span><span class="sxs-lookup"><span data-stu-id="fd9a1-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="fd9a1-115">To znamená, že pokud mají obě pole stejnou délku, a všechny prvky jsou stejné jako definované pomocí `equal` .</span><span class="sxs-lookup"><span data-stu-id="fd9a1-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fd9a1-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fd9a1-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fd9a1-117">'S</span><span class="sxs-lookup"><span data-stu-id="fd9a1-117">'T</span></span>

<span data-ttu-id="fd9a1-118">Typ prvků každého pole.</span><span class="sxs-lookup"><span data-stu-id="fd9a1-118">The type of each array's elements.</span></span>

## <a name="example"></a><span data-ttu-id="fd9a1-119">Příklad</span><span class="sxs-lookup"><span data-stu-id="fd9a1-119">Example</span></span>

<span data-ttu-id="fd9a1-120">Následující kód kontroluje, zda jsou různé páry polí stejné:</span><span class="sxs-lookup"><span data-stu-id="fd9a1-120">The following code checks whether different pairs of arrays are equal:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a><span data-ttu-id="fd9a1-121">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fd9a1-121">Remarks</span></span>

<span data-ttu-id="fd9a1-122">Tato funkce je definována pro obecné typy. To znamená, že kdykoli máme dvě pole `'T[]` a funkci `equal: ('T, 'T) -> Bool` , tato funkce vrátí `Bool` hodnotu, která označuje, zda jsou pole shodná.</span><span class="sxs-lookup"><span data-stu-id="fd9a1-122">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="fd9a1-123">Pro dvě pole, která mají být považována za EQUAL, musí mít stejnou délku a elementy ve stejné pozici v poli musí být stejné.</span><span class="sxs-lookup"><span data-stu-id="fd9a1-123">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>