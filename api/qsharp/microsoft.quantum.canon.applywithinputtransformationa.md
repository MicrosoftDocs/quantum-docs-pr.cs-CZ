---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Operace ApplyWithInputTransformationA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3ab07f301f310e3ec380981bdb53201fc74bd289
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841128"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="99971-102">Operace ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="99971-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="99971-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="99971-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="99971-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99971-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99971-105">Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.</span><span class="sxs-lookup"><span data-stu-id="99971-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="99971-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="99971-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="99971-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="99971-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="99971-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="99971-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="99971-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="99971-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="99971-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="99971-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="99971-111">vstup: U</span><span class="sxs-lookup"><span data-stu-id="99971-111">input : 'U</span></span>

<span data-ttu-id="99971-112">Vstup do funkce.</span><span class="sxs-lookup"><span data-stu-id="99971-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99971-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99971-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="99971-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="99971-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="99971-115">'S</span><span class="sxs-lookup"><span data-stu-id="99971-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="99971-116">U</span><span class="sxs-lookup"><span data-stu-id="99971-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="99971-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="99971-117">Example</span></span>

<span data-ttu-id="99971-118">Následující volání používá @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" pro použití operace navržené pro @"Microsoft.Quantum.Arithmetic.BigEndian" vstupy do vstupu typu @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="99971-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="99971-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="99971-119">See Also</span></span>

- [<span data-ttu-id="99971-120">Microsoft. proApplyWithInputTransformation. Canon.</span><span class="sxs-lookup"><span data-stu-id="99971-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="99971-121">Microsoft. proApplyWithInputTransformationC. Canon.</span><span class="sxs-lookup"><span data-stu-id="99971-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="99971-122">Microsoft. proApplyWithInputTransformationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="99971-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="99971-123">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="99971-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)