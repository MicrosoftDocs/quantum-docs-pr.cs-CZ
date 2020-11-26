---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Operace ApplyWithInputTransformationA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 8d65af33a0bc8ce3c08da54b34e68b4e22b710ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207883"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="26db8-102">Operace ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="26db8-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="26db8-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="26db8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="26db8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26db8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26db8-105">Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.</span><span class="sxs-lookup"><span data-stu-id="26db8-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="26db8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="26db8-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="26db8-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="26db8-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="26db8-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="26db8-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="26db8-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="26db8-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="26db8-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="26db8-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="26db8-111">vstup: U</span><span class="sxs-lookup"><span data-stu-id="26db8-111">input : 'U</span></span>

<span data-ttu-id="26db8-112">Vstup do funkce.</span><span class="sxs-lookup"><span data-stu-id="26db8-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="26db8-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26db8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="26db8-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="26db8-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="26db8-115">'S</span><span class="sxs-lookup"><span data-stu-id="26db8-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="26db8-116">U</span><span class="sxs-lookup"><span data-stu-id="26db8-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="26db8-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="26db8-117">See Also</span></span>

- [<span data-ttu-id="26db8-118">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="26db8-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="26db8-119">Microsoft. proApplyWithInputTransformationC. Canon.</span><span class="sxs-lookup"><span data-stu-id="26db8-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="26db8-120">Microsoft. proApplyWithInputTransformationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="26db8-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="26db8-121">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="26db8-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)