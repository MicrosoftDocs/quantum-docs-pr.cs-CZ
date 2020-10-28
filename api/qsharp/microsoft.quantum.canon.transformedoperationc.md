---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: b6867a076b654337f6127657189a8453c9973cc2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698824"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="e35aa-102">TransformedOperationC – funkce</span><span class="sxs-lookup"><span data-stu-id="e35aa-102">TransformedOperationC function</span></span>

<span data-ttu-id="e35aa-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e35aa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e35aa-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e35aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e35aa-105">Výsledkem funkce a operace je nová operace, jejíž vstup je transformovaná pomocí dané funkce.</span><span class="sxs-lookup"><span data-stu-id="e35aa-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="e35aa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e35aa-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="e35aa-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="e35aa-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="e35aa-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="e35aa-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="e35aa-109">op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="e35aa-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e35aa-110">Operace, která se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="e35aa-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-ctl"></a><span data-ttu-id="e35aa-111">Výstup: U [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="e35aa-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e35aa-112">Nová operace tbat volání `fn` s jeho vstupem a pak předává výsledný výstup do `op` .</span><span class="sxs-lookup"><span data-stu-id="e35aa-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e35aa-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e35aa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e35aa-114">'S</span><span class="sxs-lookup"><span data-stu-id="e35aa-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="e35aa-115">U</span><span class="sxs-lookup"><span data-stu-id="e35aa-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="e35aa-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="e35aa-116">See Also</span></span>

- [<span data-ttu-id="e35aa-117">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="e35aa-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="e35aa-118">Microsoft. proTransformedOperationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e35aa-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="e35aa-119">Microsoft. proTransformedOperationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e35aa-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="e35aa-120">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="e35aa-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="e35aa-121">Microsoft... Canon. složeno</span><span class="sxs-lookup"><span data-stu-id="e35aa-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)