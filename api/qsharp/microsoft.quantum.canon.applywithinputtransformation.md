---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Operace ApplyWithInputTransformation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d4589acbe9f9dc6c6ab665582ed663dbc193edbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850372"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="0d21a-102">Operace ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="0d21a-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="0d21a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0d21a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0d21a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d21a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d21a-105">Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.</span><span class="sxs-lookup"><span data-stu-id="0d21a-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="0d21a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0d21a-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="0d21a-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="0d21a-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="0d21a-108">Funkce, která transformuje daný vstup do formuláře očekávaného operací.</span><span class="sxs-lookup"><span data-stu-id="0d21a-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="0d21a-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d21a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0d21a-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="0d21a-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="0d21a-111">vstup: U</span><span class="sxs-lookup"><span data-stu-id="0d21a-111">input : 'U</span></span>

<span data-ttu-id="0d21a-112">Vstup do funkce.</span><span class="sxs-lookup"><span data-stu-id="0d21a-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d21a-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d21a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0d21a-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0d21a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d21a-115">'S</span><span class="sxs-lookup"><span data-stu-id="0d21a-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="0d21a-116">U</span><span class="sxs-lookup"><span data-stu-id="0d21a-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="0d21a-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="0d21a-117">Example</span></span>

<span data-ttu-id="0d21a-118">Následující volání používá @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" pro použití operace navržené pro @"Microsoft.Quantum.Arithmetic.BigEndian" vstupy do vstupu typu @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="0d21a-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="0d21a-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="0d21a-119">See Also</span></span>

- [<span data-ttu-id="0d21a-120">Microsoft. proApplyWithInputTransformationA. Canon.</span><span class="sxs-lookup"><span data-stu-id="0d21a-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="0d21a-121">Microsoft. proApplyWithInputTransformationC. Canon.</span><span class="sxs-lookup"><span data-stu-id="0d21a-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="0d21a-122">Microsoft. proApplyWithInputTransformationCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="0d21a-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="0d21a-123">Microsoft. proTransformedOperation. Canon.</span><span class="sxs-lookup"><span data-stu-id="0d21a-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)