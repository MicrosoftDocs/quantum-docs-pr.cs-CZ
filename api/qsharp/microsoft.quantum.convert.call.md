---
uid: Microsoft.Quantum.Convert.Call
title: Operace volání
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850195"
---
# <a name="call-operation"></a><span data-ttu-id="79e1f-102">Operace volání</span><span class="sxs-lookup"><span data-stu-id="79e1f-102">Call operation</span></span>

<span data-ttu-id="79e1f-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="79e1f-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="79e1f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79e1f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79e1f-105">Volá funkci s daným vstupem.</span><span class="sxs-lookup"><span data-stu-id="79e1f-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="79e1f-106">Popis</span><span class="sxs-lookup"><span data-stu-id="79e1f-106">Description</span></span>

<span data-ttu-id="79e1f-107">Při zadání funkce a vstupu do této funkce volá funkci a vrátí její výstup.</span><span class="sxs-lookup"><span data-stu-id="79e1f-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="79e1f-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="79e1f-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="79e1f-109">FN: výstup Input-></span><span class="sxs-lookup"><span data-stu-id="79e1f-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="79e1f-110">Funkce, která má být volána.</span><span class="sxs-lookup"><span data-stu-id="79e1f-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="79e1f-111">Input: Input</span><span class="sxs-lookup"><span data-stu-id="79e1f-111">input : 'Input</span></span>

<span data-ttu-id="79e1f-112">Vstup, který má být předán do funkce.</span><span class="sxs-lookup"><span data-stu-id="79e1f-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="79e1f-113">Výstup: Output</span><span class="sxs-lookup"><span data-stu-id="79e1f-113">Output : 'Output</span></span>

<span data-ttu-id="79e1f-114">Výsledek volání funkce `fn`.</span><span class="sxs-lookup"><span data-stu-id="79e1f-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="79e1f-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="79e1f-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="79e1f-116">Vstup</span><span class="sxs-lookup"><span data-stu-id="79e1f-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="79e1f-117">Výstup</span><span class="sxs-lookup"><span data-stu-id="79e1f-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="79e1f-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="79e1f-118">Remarks</span></span>

<span data-ttu-id="79e1f-119">Tato operace je hlavně užitečná pro vynucení volání funkce na konkrétní místo v rámci operace nebo pro volání funkce, kde je očekávána operace.</span><span class="sxs-lookup"><span data-stu-id="79e1f-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>