---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operace opakování
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 9ae3123a64b2a886df3b7575b2840522f9b011ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852224"
---
# <a name="repeata-operation"></a><span data-ttu-id="ddf62-102">Operace opakování</span><span class="sxs-lookup"><span data-stu-id="ddf62-102">RepeatA operation</span></span>

<span data-ttu-id="ddf62-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ddf62-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ddf62-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddf62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddf62-105">Opakuje zadaný počet opakování operace.</span><span class="sxs-lookup"><span data-stu-id="ddf62-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ddf62-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ddf62-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="ddf62-107">op: TInput => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="ddf62-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ddf62-108">Operace, která se má volat opakovaně</span><span class="sxs-lookup"><span data-stu-id="ddf62-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="ddf62-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ddf62-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ddf62-110">Počet pokusů o volání `op` .</span><span class="sxs-lookup"><span data-stu-id="ddf62-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="ddf62-111">vstup: ' TInput</span><span class="sxs-lookup"><span data-stu-id="ddf62-111">input : 'TInput</span></span>

<span data-ttu-id="ddf62-112">Vstup, který má být předán `op` .</span><span class="sxs-lookup"><span data-stu-id="ddf62-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ddf62-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ddf62-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ddf62-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ddf62-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="ddf62-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="ddf62-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="ddf62-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="ddf62-116">Example</span></span>

<span data-ttu-id="ddf62-117">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="ddf62-117">The following are equivalent:</span></span>

```qsharp
RepeatA(U, 17, target);
(BoundA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="ddf62-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="ddf62-118">See Also</span></span>

- [<span data-ttu-id="ddf62-119">Microsoft. Forms. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="ddf62-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="ddf62-120">Microsoft. v. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="ddf62-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="ddf62-121">Microsoft. proRepeatC. Canon.</span><span class="sxs-lookup"><span data-stu-id="ddf62-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="ddf62-122">Microsoft. proRepeatCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="ddf62-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)