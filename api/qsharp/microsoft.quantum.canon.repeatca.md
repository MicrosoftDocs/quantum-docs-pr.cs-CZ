---
uid: Microsoft.Quantum.Canon.RepeatCA
title: Operace RepeatCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: af93220562d6be27b2f41e770bd953e5e808fcbf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852209"
---
# <a name="repeatca-operation"></a><span data-ttu-id="5a589-102">Operace RepeatCA</span><span class="sxs-lookup"><span data-stu-id="5a589-102">RepeatCA operation</span></span>

<span data-ttu-id="5a589-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5a589-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5a589-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a589-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a589-105">Opakuje zadaný počet opakování operace.</span><span class="sxs-lookup"><span data-stu-id="5a589-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5a589-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5a589-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="5a589-107">op: TInput => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="5a589-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="5a589-108">Operace, která se má volat opakovaně</span><span class="sxs-lookup"><span data-stu-id="5a589-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="5a589-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a589-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a589-110">Počet pokusů o volání `op` .</span><span class="sxs-lookup"><span data-stu-id="5a589-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="5a589-111">vstup: ' TInput</span><span class="sxs-lookup"><span data-stu-id="5a589-111">input : 'TInput</span></span>

<span data-ttu-id="5a589-112">Vstup, který má být předán `op` .</span><span class="sxs-lookup"><span data-stu-id="5a589-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a589-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a589-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5a589-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5a589-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="5a589-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="5a589-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="5a589-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="5a589-116">Example</span></span>

<span data-ttu-id="5a589-117">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="5a589-117">The following are equivalent:</span></span>

```qsharp
RepeatCA(U, 17, target);
(BoundCA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="5a589-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="5a589-118">See Also</span></span>

- [<span data-ttu-id="5a589-119">Microsoft. Forms. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="5a589-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="5a589-120">Microsoft. v. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="5a589-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="5a589-121">Microsoft. prodoby. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="5a589-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="5a589-122">Microsoft. proRepeatC. Canon.</span><span class="sxs-lookup"><span data-stu-id="5a589-122">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)