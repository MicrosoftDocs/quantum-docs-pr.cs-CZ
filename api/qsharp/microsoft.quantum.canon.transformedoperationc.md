---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 964576788bc80dd8920acdfb62d5d69a060e75f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204857"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="c9f66-102">TransformedOperationC – funkce</span><span class="sxs-lookup"><span data-stu-id="c9f66-102">TransformedOperationC function</span></span>

<span data-ttu-id="c9f66-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9f66-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9f66-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9f66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9f66-105">Výsledkem funkce a operace je nová operace, jejíž vstup je transformovaná pomocí dané funkce.</span><span class="sxs-lookup"><span data-stu-id="c9f66-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c9f66-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c9f66-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="c9f66-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="c9f66-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="c9f66-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="c9f66-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="c9f66-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="c9f66-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c9f66-110">Operace, která se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="c9f66-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-ctl"></a><span data-ttu-id="c9f66-111">Výstup: U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL.</span><span class="sxs-lookup"><span data-stu-id="c9f66-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c9f66-112">Nová operace tbat volání `fn` s jeho vstupem a pak předává výsledný výstup do `op` .</span><span class="sxs-lookup"><span data-stu-id="c9f66-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c9f66-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c9f66-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9f66-114">'S</span><span class="sxs-lookup"><span data-stu-id="c9f66-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="c9f66-115">U</span><span class="sxs-lookup"><span data-stu-id="c9f66-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="c9f66-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="c9f66-116">See Also</span></span>

- [<span data-ttu-id="c9f66-117">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="c9f66-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="c9f66-118">Microsoft. proTransformedOperationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="c9f66-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="c9f66-119">Microsoft. proTransformedOperationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="c9f66-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="c9f66-120">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="c9f66-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="c9f66-121">Microsoft... Canon. složeno</span><span class="sxs-lookup"><span data-stu-id="c9f66-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)