---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Operace ApplyWithInputTransformation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3586e9a114a550fb1989186e9c18fe4f344cf060
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217182"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="e83b6-102">Operace ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="e83b6-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="e83b6-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e83b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e83b6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e83b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e83b6-105">Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.</span><span class="sxs-lookup"><span data-stu-id="e83b6-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="e83b6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e83b6-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="e83b6-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="e83b6-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="e83b6-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="e83b6-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="e83b6-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e83b6-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e83b6-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="e83b6-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="e83b6-111">vstup: U</span><span class="sxs-lookup"><span data-stu-id="e83b6-111">input : 'U</span></span>

<span data-ttu-id="e83b6-112">Vstup do funkce.</span><span class="sxs-lookup"><span data-stu-id="e83b6-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e83b6-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e83b6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e83b6-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e83b6-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e83b6-115">'S</span><span class="sxs-lookup"><span data-stu-id="e83b6-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="e83b6-116">U</span><span class="sxs-lookup"><span data-stu-id="e83b6-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="e83b6-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="e83b6-117">See Also</span></span>

- [<span data-ttu-id="e83b6-118">Microsoft. proApplyWithInputTransformationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e83b6-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="e83b6-119">Microsoft. proApplyWithInputTransformationC. Canon.</span><span class="sxs-lookup"><span data-stu-id="e83b6-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="e83b6-120">Microsoft. proApplyWithInputTransformationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e83b6-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="e83b6-121">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="e83b6-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)