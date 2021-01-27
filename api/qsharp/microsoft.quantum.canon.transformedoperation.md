---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852059"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="16ee6-102">TransformedOperation – funkce</span><span class="sxs-lookup"><span data-stu-id="16ee6-102">TransformedOperation function</span></span>

<span data-ttu-id="16ee6-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="16ee6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="16ee6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16ee6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16ee6-105">Výsledkem funkce a operace je nová operace, jejíž vstup je transformovaná pomocí dané funkce.</span><span class="sxs-lookup"><span data-stu-id="16ee6-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="16ee6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="16ee6-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="16ee6-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="16ee6-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="16ee6-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="16ee6-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="16ee6-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16ee6-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="16ee6-110">Operace, která se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="16ee6-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="16ee6-111">Výstup: ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16ee6-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="16ee6-112">Nová operace tbat volání `fn` s jeho vstupem a pak předává výsledný výstup do `op` .</span><span class="sxs-lookup"><span data-stu-id="16ee6-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="16ee6-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="16ee6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16ee6-114">'S</span><span class="sxs-lookup"><span data-stu-id="16ee6-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="16ee6-115">U</span><span class="sxs-lookup"><span data-stu-id="16ee6-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="16ee6-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="16ee6-116">Example</span></span>

<span data-ttu-id="16ee6-117">Následující volání slouží @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" k transformaci operace navržené pro @"Microsoft.Quantum.Arithmetic.BigEndian" vstupy do operace, která přijímá vstupy typu @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="16ee6-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="16ee6-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="16ee6-118">See Also</span></span>

- [<span data-ttu-id="16ee6-119">Microsoft. proTransformedOperationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="16ee6-119">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="16ee6-120">Microsoft. proTransformedOperationC. Canon.</span><span class="sxs-lookup"><span data-stu-id="16ee6-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="16ee6-121">Microsoft. proTransformedOperationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="16ee6-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="16ee6-122">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="16ee6-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="16ee6-123">Microsoft... Canon. složeno</span><span class="sxs-lookup"><span data-stu-id="16ee6-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)