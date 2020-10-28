---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 349424a102dba7354bbaa65fffdc2b5d506a3b91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698825"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="00d83-102">TransformedOperationA – funkce</span><span class="sxs-lookup"><span data-stu-id="00d83-102">TransformedOperationA function</span></span>

<span data-ttu-id="00d83-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="00d83-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="00d83-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00d83-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00d83-105">Výsledkem funkce a operace je nová operace, jejíž vstup je transformovaná pomocí dané funkce.</span><span class="sxs-lookup"><span data-stu-id="00d83-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="00d83-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="00d83-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="00d83-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="00d83-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="00d83-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="00d83-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="00d83-109">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00d83-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="00d83-110">Operace, která se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="00d83-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-adj"></a><span data-ttu-id="00d83-111">Výstup: U =>á [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="00d83-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="00d83-112">Nová operace tbat volání `fn` s jeho vstupem a pak předává výsledný výstup do `op` .</span><span class="sxs-lookup"><span data-stu-id="00d83-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="00d83-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="00d83-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="00d83-114">'S</span><span class="sxs-lookup"><span data-stu-id="00d83-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="00d83-115">U</span><span class="sxs-lookup"><span data-stu-id="00d83-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="00d83-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="00d83-116">See Also</span></span>

- [<span data-ttu-id="00d83-117">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="00d83-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="00d83-118">Microsoft. proTransformedOperationC. Canon.</span><span class="sxs-lookup"><span data-stu-id="00d83-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="00d83-119">Microsoft. proTransformedOperationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="00d83-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="00d83-120">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="00d83-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="00d83-121">Microsoft... Canon. složeno</span><span class="sxs-lookup"><span data-stu-id="00d83-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)