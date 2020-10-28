---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Operace ApplyWithInputTransformationC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: f166880d3ca8a7fc45635c0105aa5c83fe1b4f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704553"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="64d8e-102">Operace ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="64d8e-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="64d8e-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64d8e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64d8e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64d8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64d8e-105">Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.</span><span class="sxs-lookup"><span data-stu-id="64d8e-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="64d8e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="64d8e-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="64d8e-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="64d8e-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="64d8e-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="64d8e-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="64d8e-109">op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="64d8e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="64d8e-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="64d8e-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="64d8e-111">vstup: U</span><span class="sxs-lookup"><span data-stu-id="64d8e-111">input : 'U</span></span>

<span data-ttu-id="64d8e-112">Vstup do funkce.</span><span class="sxs-lookup"><span data-stu-id="64d8e-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="64d8e-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64d8e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="64d8e-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="64d8e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64d8e-115">'S</span><span class="sxs-lookup"><span data-stu-id="64d8e-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="64d8e-116">U</span><span class="sxs-lookup"><span data-stu-id="64d8e-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="64d8e-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="64d8e-117">See Also</span></span>

- [<span data-ttu-id="64d8e-118">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="64d8e-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="64d8e-119">Microsoft. proApplyWithInputTransformationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="64d8e-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="64d8e-120">Microsoft. proApplyWithInputTransformationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="64d8e-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="64d8e-121">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="64d8e-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)