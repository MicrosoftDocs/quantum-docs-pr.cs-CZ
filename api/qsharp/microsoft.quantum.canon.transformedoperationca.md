---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fa204433dc8195dd27fa40980fb2262f8a3848bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204840"
---
# <a name="transformedoperationca-function"></a><span data-ttu-id="bcb2c-102">TransformedOperationCA – funkce</span><span class="sxs-lookup"><span data-stu-id="bcb2c-102">TransformedOperationCA function</span></span>

<span data-ttu-id="bcb2c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bcb2c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bcb2c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bcb2c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bcb2c-105">Výsledkem funkce a operace je nová operace, jejíž vstup je transformovaná pomocí dané funkce.</span><span class="sxs-lookup"><span data-stu-id="bcb2c-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="bcb2c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bcb2c-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="bcb2c-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="bcb2c-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="bcb2c-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="bcb2c-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="bcb2c-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="bcb2c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bcb2c-110">Operace, která se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="bcb2c-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj--ctl"></a><span data-ttu-id="bcb2c-111">Výstup: ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="bcb2c-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bcb2c-112">Nová operace tbat volání `fn` s jeho vstupem a pak předává výsledný výstup do `op` .</span><span class="sxs-lookup"><span data-stu-id="bcb2c-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bcb2c-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bcb2c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bcb2c-114">'S</span><span class="sxs-lookup"><span data-stu-id="bcb2c-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="bcb2c-115">U</span><span class="sxs-lookup"><span data-stu-id="bcb2c-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="bcb2c-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="bcb2c-116">See Also</span></span>

- [<span data-ttu-id="bcb2c-117">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="bcb2c-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="bcb2c-118">Microsoft. proTransformedOperationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="bcb2c-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="bcb2c-119">Microsoft. proTransformedOperationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="bcb2c-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="bcb2c-120">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="bcb2c-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="bcb2c-121">Microsoft... Canon. složeno</span><span class="sxs-lookup"><span data-stu-id="bcb2c-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)