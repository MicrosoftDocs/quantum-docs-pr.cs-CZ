---
uid: Microsoft.Quantum.Arrays.Any
title: Libovolná funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706177"
---
# <a name="any-function"></a><span data-ttu-id="38f9f-102">Libovolná funkce</span><span class="sxs-lookup"><span data-stu-id="38f9f-102">Any function</span></span>

<span data-ttu-id="38f9f-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="38f9f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="38f9f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38f9f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38f9f-105">V případě pole a predikátu, který je definován pro prvky pole, zkontroluje, zda alespoň jeden prvek pole splňuje predikát.</span><span class="sxs-lookup"><span data-stu-id="38f9f-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="38f9f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="38f9f-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="38f9f-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="38f9f-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="38f9f-108">Funkce z `'T` `Bool` , která se používá ke kontrole prvků.</span><span class="sxs-lookup"><span data-stu-id="38f9f-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="38f9f-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="38f9f-109">array : 'T[]</span></span>

<span data-ttu-id="38f9f-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="38f9f-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="38f9f-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="38f9f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="38f9f-112">`Bool`Hodnota nebo funkce predikátu použité pro všechny elementy.</span><span class="sxs-lookup"><span data-stu-id="38f9f-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="38f9f-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="38f9f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="38f9f-114">'S</span><span class="sxs-lookup"><span data-stu-id="38f9f-114">'T</span></span>

<span data-ttu-id="38f9f-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="38f9f-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="38f9f-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="38f9f-116">Remarks</span></span>

<span data-ttu-id="38f9f-117">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a funkci, `predicate: 'T -> Bool` můžeme vytvořit `Bool` hodnotu, která označuje, zda určitý prvek splňuje požadavky `predicate` .</span><span class="sxs-lookup"><span data-stu-id="38f9f-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>