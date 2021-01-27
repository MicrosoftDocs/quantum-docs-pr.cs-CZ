---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operace DrawMany
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846208"
---
# <a name="drawmany-operation"></a><span data-ttu-id="b5d74-102">Operace DrawMany</span><span class="sxs-lookup"><span data-stu-id="b5d74-102">DrawMany operation</span></span>

<span data-ttu-id="b5d74-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b5d74-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b5d74-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5d74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5d74-105">Opakuje operaci pro daný počet vzorků a shromažďuje jejich výstupy v poli.</span><span class="sxs-lookup"><span data-stu-id="b5d74-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="b5d74-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b5d74-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="b5d74-107">op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="b5d74-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="b5d74-108">Operace, která se má volat opakovaně</span><span class="sxs-lookup"><span data-stu-id="b5d74-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="b5d74-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5d74-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5d74-110">Počet vzorků volání `op` ke shromáždění.</span><span class="sxs-lookup"><span data-stu-id="b5d74-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="b5d74-111">vstup: ' TInput</span><span class="sxs-lookup"><span data-stu-id="b5d74-111">input : 'TInput</span></span>

<span data-ttu-id="b5d74-112">Vstup, který má být předán `op` .</span><span class="sxs-lookup"><span data-stu-id="b5d74-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="b5d74-113">Výstup: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="b5d74-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b5d74-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b5d74-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="b5d74-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="b5d74-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="b5d74-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="b5d74-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="b5d74-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="b5d74-117">Example</span></span>

<span data-ttu-id="b5d74-118">Následující ukázky celé číslo, s ohledem na operaci, která v jednom okamžiku vyčísluje jeden bit.</span><span class="sxs-lookup"><span data-stu-id="b5d74-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="b5d74-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="b5d74-119">See Also</span></span>

- [<span data-ttu-id="b5d74-120">Microsoft. v. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="b5d74-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)