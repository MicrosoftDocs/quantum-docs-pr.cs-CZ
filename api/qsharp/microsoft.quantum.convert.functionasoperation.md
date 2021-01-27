---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833826"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="8e10d-102">FunctionAsOperation – funkce</span><span class="sxs-lookup"><span data-stu-id="8e10d-102">FunctionAsOperation function</span></span>

<span data-ttu-id="8e10d-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="8e10d-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="8e10d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e10d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e10d-105">Převede funkce na operace.</span><span class="sxs-lookup"><span data-stu-id="8e10d-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="8e10d-106">Popis</span><span class="sxs-lookup"><span data-stu-id="8e10d-106">Description</span></span>

<span data-ttu-id="8e10d-107">V případě funkce vrátí operaci, která volá tuto funkci, a která nedělá nic jiného.</span><span class="sxs-lookup"><span data-stu-id="8e10d-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="8e10d-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="8e10d-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="8e10d-109">FN: výstup Input-></span><span class="sxs-lookup"><span data-stu-id="8e10d-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="8e10d-110">Funkce, která má být převedena na operaci.</span><span class="sxs-lookup"><span data-stu-id="8e10d-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="8e10d-111">Výstup: Input => – výstup</span><span class="sxs-lookup"><span data-stu-id="8e10d-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="8e10d-112">Operace `op` , která `op(input)` je stejná jako `fn(input)` u všech `input` .</span><span class="sxs-lookup"><span data-stu-id="8e10d-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8e10d-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8e10d-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="8e10d-114">Vstup</span><span class="sxs-lookup"><span data-stu-id="8e10d-114">'Input</span></span>

<span data-ttu-id="8e10d-115">Typ vstupu funkce, která má být převedena.</span><span class="sxs-lookup"><span data-stu-id="8e10d-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="8e10d-116">Výstup</span><span class="sxs-lookup"><span data-stu-id="8e10d-116">'Output</span></span>

<span data-ttu-id="8e10d-117">Typ výstupu funkce, která má být převedena.</span><span class="sxs-lookup"><span data-stu-id="8e10d-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e10d-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8e10d-118">Remarks</span></span>

<span data-ttu-id="8e10d-119">To je užitečné hlavně při předávání funkcí funkcí nebo operací, které očekávají operaci jako vstup.</span><span class="sxs-lookup"><span data-stu-id="8e10d-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>