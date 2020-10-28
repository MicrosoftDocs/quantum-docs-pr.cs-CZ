---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Operace ApplyWithInputTransformationA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b72c131691e08b4bd32b7faf9265aad6c52b7fde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704560"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="57459-102">Operace ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="57459-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="57459-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57459-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57459-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57459-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57459-105">Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.</span><span class="sxs-lookup"><span data-stu-id="57459-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="57459-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="57459-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="57459-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="57459-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="57459-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="57459-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="57459-109">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57459-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="57459-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="57459-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="57459-111">vstup: U</span><span class="sxs-lookup"><span data-stu-id="57459-111">input : 'U</span></span>

<span data-ttu-id="57459-112">Vstup do funkce.</span><span class="sxs-lookup"><span data-stu-id="57459-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57459-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57459-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="57459-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="57459-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57459-115">'S</span><span class="sxs-lookup"><span data-stu-id="57459-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="57459-116">U</span><span class="sxs-lookup"><span data-stu-id="57459-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="57459-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="57459-117">See Also</span></span>

- [<span data-ttu-id="57459-118">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="57459-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="57459-119">Microsoft. proApplyWithInputTransformationC. Canon.</span><span class="sxs-lookup"><span data-stu-id="57459-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="57459-120">Microsoft. proApplyWithInputTransformationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="57459-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="57459-121">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="57459-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)