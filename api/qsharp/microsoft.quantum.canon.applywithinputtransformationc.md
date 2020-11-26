---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Operace ApplyWithInputTransformationC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 030c41d3ce0a5d613a95c6511f7278497ec5cda1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217165"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="43bef-102">Operace ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="43bef-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="43bef-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="43bef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="43bef-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43bef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43bef-105">Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.</span><span class="sxs-lookup"><span data-stu-id="43bef-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="43bef-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="43bef-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="43bef-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="43bef-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="43bef-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="43bef-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="43bef-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="43bef-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="43bef-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="43bef-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="43bef-111">vstup: U</span><span class="sxs-lookup"><span data-stu-id="43bef-111">input : 'U</span></span>

<span data-ttu-id="43bef-112">Vstup do funkce.</span><span class="sxs-lookup"><span data-stu-id="43bef-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="43bef-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="43bef-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="43bef-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="43bef-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="43bef-115">'S</span><span class="sxs-lookup"><span data-stu-id="43bef-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="43bef-116">U</span><span class="sxs-lookup"><span data-stu-id="43bef-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="43bef-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="43bef-117">See Also</span></span>

- [<span data-ttu-id="43bef-118">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="43bef-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="43bef-119">Microsoft. proApplyWithInputTransformationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="43bef-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="43bef-120">Microsoft. proApplyWithInputTransformationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="43bef-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="43bef-121">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="43bef-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)