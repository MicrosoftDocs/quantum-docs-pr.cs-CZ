---
uid: Microsoft.Quantum.Convert.Call
title: Operace volání
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214207"
---
# <a name="call-operation"></a><span data-ttu-id="fbcc2-102">Operace volání</span><span class="sxs-lookup"><span data-stu-id="fbcc2-102">Call operation</span></span>

<span data-ttu-id="fbcc2-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="fbcc2-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="fbcc2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbcc2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbcc2-105">Volá funkci s daným vstupem.</span><span class="sxs-lookup"><span data-stu-id="fbcc2-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="fbcc2-106">Popis</span><span class="sxs-lookup"><span data-stu-id="fbcc2-106">Description</span></span>

<span data-ttu-id="fbcc2-107">Při zadání funkce a vstupu do této funkce volá funkci a vrátí její výstup.</span><span class="sxs-lookup"><span data-stu-id="fbcc2-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="fbcc2-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="fbcc2-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="fbcc2-109">FN: výstup Input-></span><span class="sxs-lookup"><span data-stu-id="fbcc2-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="fbcc2-110">Funkce, která má být volána.</span><span class="sxs-lookup"><span data-stu-id="fbcc2-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="fbcc2-111">Input: Input</span><span class="sxs-lookup"><span data-stu-id="fbcc2-111">input : 'Input</span></span>

<span data-ttu-id="fbcc2-112">Vstup, který má být předán do funkce.</span><span class="sxs-lookup"><span data-stu-id="fbcc2-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="fbcc2-113">Výstup: Output</span><span class="sxs-lookup"><span data-stu-id="fbcc2-113">Output : 'Output</span></span>

<span data-ttu-id="fbcc2-114">Výsledek volání funkce `fn`.</span><span class="sxs-lookup"><span data-stu-id="fbcc2-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fbcc2-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fbcc2-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="fbcc2-116">Vstup</span><span class="sxs-lookup"><span data-stu-id="fbcc2-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="fbcc2-117">Výstup</span><span class="sxs-lookup"><span data-stu-id="fbcc2-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="fbcc2-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fbcc2-118">Remarks</span></span>

<span data-ttu-id="fbcc2-119">Tato operace je hlavně užitečná pro vynucení volání funkce na konkrétní místo v rámci operace nebo pro volání funkce, kde je očekávána operace.</span><span class="sxs-lookup"><span data-stu-id="fbcc2-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>