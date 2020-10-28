---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698828"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="bf6f1-102">TransformedOperation – funkce</span><span class="sxs-lookup"><span data-stu-id="bf6f1-102">TransformedOperation function</span></span>

<span data-ttu-id="bf6f1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bf6f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bf6f1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf6f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf6f1-105">Výsledkem funkce a operace je nová operace, jejíž vstup je transformovaná pomocí dané funkce.</span><span class="sxs-lookup"><span data-stu-id="bf6f1-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="bf6f1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bf6f1-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="bf6f1-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="bf6f1-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="bf6f1-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="bf6f1-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="bf6f1-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf6f1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bf6f1-110">Operace, která se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="bf6f1-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="bf6f1-111">Výstup: ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf6f1-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bf6f1-112">Nová operace tbat volání `fn` s jeho vstupem a pak předává výsledný výstup do `op` .</span><span class="sxs-lookup"><span data-stu-id="bf6f1-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bf6f1-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bf6f1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf6f1-114">'S</span><span class="sxs-lookup"><span data-stu-id="bf6f1-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="bf6f1-115">U</span><span class="sxs-lookup"><span data-stu-id="bf6f1-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="bf6f1-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="bf6f1-116">See Also</span></span>

- [<span data-ttu-id="bf6f1-117">Microsoft. proTransformedOperationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="bf6f1-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="bf6f1-118">Microsoft. proTransformedOperationC. Canon.</span><span class="sxs-lookup"><span data-stu-id="bf6f1-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="bf6f1-119">Microsoft. proTransformedOperationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="bf6f1-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="bf6f1-120">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="bf6f1-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="bf6f1-121">Microsoft... Canon. složeno</span><span class="sxs-lookup"><span data-stu-id="bf6f1-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)