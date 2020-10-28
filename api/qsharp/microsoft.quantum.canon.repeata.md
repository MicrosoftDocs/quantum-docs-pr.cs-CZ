---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operace opakování
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698892"
---
# <a name="repeata-operation"></a><span data-ttu-id="c6791-102">Operace opakování</span><span class="sxs-lookup"><span data-stu-id="c6791-102">RepeatA operation</span></span>

<span data-ttu-id="c6791-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6791-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6791-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6791-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6791-105">Opakuje zadaný počet opakování operace.</span><span class="sxs-lookup"><span data-stu-id="c6791-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="c6791-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c6791-106">Input</span></span>

### <a name="op--tinput--unit-adj"></a><span data-ttu-id="c6791-107">op: TInput => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6791-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c6791-108">Operace, která se má volat opakovaně</span><span class="sxs-lookup"><span data-stu-id="c6791-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="c6791-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6791-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6791-110">Počet pokusů o volání `op` .</span><span class="sxs-lookup"><span data-stu-id="c6791-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="c6791-111">vstup: ' TInput</span><span class="sxs-lookup"><span data-stu-id="c6791-111">input : 'TInput</span></span>

<span data-ttu-id="c6791-112">Vstup, který má být předán `op` .</span><span class="sxs-lookup"><span data-stu-id="c6791-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6791-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6791-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c6791-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c6791-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="c6791-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="c6791-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="c6791-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="c6791-116">See Also</span></span>

- [<span data-ttu-id="c6791-117">Microsoft. Forms. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="c6791-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="c6791-118">Microsoft. v. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="c6791-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="c6791-119">Microsoft. proRepeatC. Canon.</span><span class="sxs-lookup"><span data-stu-id="c6791-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="c6791-120">Microsoft. proRepeatCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="c6791-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)