---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Operace ApplyWithInputTransformationCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c81620555bff9449d6a3235dc7cfa56ca5206f04
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207781"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="8664f-102">Operace ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="8664f-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="8664f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8664f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8664f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8664f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8664f-105">Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.</span><span class="sxs-lookup"><span data-stu-id="8664f-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8664f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8664f-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="8664f-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="8664f-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="8664f-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="8664f-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="8664f-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="8664f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8664f-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="8664f-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="8664f-111">vstup: U</span><span class="sxs-lookup"><span data-stu-id="8664f-111">input : 'U</span></span>

<span data-ttu-id="8664f-112">Vstup do funkce.</span><span class="sxs-lookup"><span data-stu-id="8664f-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8664f-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8664f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8664f-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8664f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8664f-115">'S</span><span class="sxs-lookup"><span data-stu-id="8664f-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="8664f-116">U</span><span class="sxs-lookup"><span data-stu-id="8664f-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="8664f-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="8664f-117">See Also</span></span>

- [<span data-ttu-id="8664f-118">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="8664f-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="8664f-119">Microsoft. proApplyWithInputTransformationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8664f-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="8664f-120">Microsoft. proApplyWithInputTransformationC. Canon.</span><span class="sxs-lookup"><span data-stu-id="8664f-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="8664f-121">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="8664f-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)