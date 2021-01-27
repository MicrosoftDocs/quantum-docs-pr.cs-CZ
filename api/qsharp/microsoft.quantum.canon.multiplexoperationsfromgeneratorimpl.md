---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGeneratorImpl
title: Operace MultiplexOperationsFromGeneratorImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGeneratorImpl
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 68c9fcf7ee7893dc3ef6600cc5d6c5be807f9eb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852487"
---
# <a name="multiplexoperationsfromgeneratorimpl-operation"></a><span data-ttu-id="a6b7b-102">Operace MultiplexOperationsFromGeneratorImpl</span><span class="sxs-lookup"><span data-stu-id="a6b7b-102">MultiplexOperationsFromGeneratorImpl operation</span></span>

<span data-ttu-id="a6b7b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a6b7b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a6b7b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6b7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6b7b-105">Krok implementace `MultiplexOperationsFromGenerator` .</span><span class="sxs-lookup"><span data-stu-id="a6b7b-105">Implementation step of `MultiplexOperationsFromGenerator`.</span></span>

```qsharp
operation MultiplexOperationsFromGeneratorImpl<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a6b7b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a6b7b-106">Input</span></span>

### <a name="unitarygenerator--intintint---t--unit--is-adj--ctl"></a><span data-ttu-id="a6b7b-107">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="a6b7b-107">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="a6b7b-108">Pomocná: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a6b7b-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="a6b7b-109">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a6b7b-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="a6b7b-110">cíl: t</span><span class="sxs-lookup"><span data-stu-id="a6b7b-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="a6b7b-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6b7b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a6b7b-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a6b7b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a6b7b-113">'S</span><span class="sxs-lookup"><span data-stu-id="a6b7b-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="a6b7b-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="a6b7b-114">See Also</span></span>

- [<span data-ttu-id="a6b7b-115">Microsoft. proMultiplexOperationsFromGenerator. Canon.</span><span class="sxs-lookup"><span data-stu-id="a6b7b-115">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)