---
uid: Microsoft.Quantum.Canon.Repeat
title: Opakovat operaci
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 40ee191e8d9044f33aa1621303c70f7e0847e8f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852249"
---
# <a name="repeat-operation"></a><span data-ttu-id="75d22-102">Opakovat operaci</span><span class="sxs-lookup"><span data-stu-id="75d22-102">Repeat operation</span></span>

<span data-ttu-id="75d22-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="75d22-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="75d22-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75d22-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75d22-105">Opakuje zadaný počet opakování operace.</span><span class="sxs-lookup"><span data-stu-id="75d22-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="75d22-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="75d22-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="75d22-107">op: TInput => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75d22-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="75d22-108">Operace, která se má volat opakovaně</span><span class="sxs-lookup"><span data-stu-id="75d22-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="75d22-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="75d22-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="75d22-110">Počet pokusů o volání `op` .</span><span class="sxs-lookup"><span data-stu-id="75d22-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="75d22-111">vstup: ' TInput</span><span class="sxs-lookup"><span data-stu-id="75d22-111">input : 'TInput</span></span>

<span data-ttu-id="75d22-112">Vstup, který má být předán `op` .</span><span class="sxs-lookup"><span data-stu-id="75d22-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="75d22-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75d22-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="75d22-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="75d22-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="75d22-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="75d22-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="75d22-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="75d22-116">Example</span></span>

<span data-ttu-id="75d22-117">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="75d22-117">The following are equivalent:</span></span>

```qsharp
Repeat(U, 17, target);
(Bound(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="75d22-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="75d22-118">See Also</span></span>

- [<span data-ttu-id="75d22-119">Microsoft. Forms. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="75d22-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="75d22-120">Microsoft. prodoby. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="75d22-120">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="75d22-121">Microsoft. proRepeatC. Canon.</span><span class="sxs-lookup"><span data-stu-id="75d22-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="75d22-122">Microsoft. proRepeatCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="75d22-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)