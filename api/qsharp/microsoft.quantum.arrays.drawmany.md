---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operace DrawMany
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209991"
---
# <a name="drawmany-operation"></a><span data-ttu-id="f01e9-102">Operace DrawMany</span><span class="sxs-lookup"><span data-stu-id="f01e9-102">DrawMany operation</span></span>

<span data-ttu-id="f01e9-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f01e9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f01e9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f01e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f01e9-105">Opakuje operaci pro daný počet vzorků a shromažďuje jejich výstupy v poli.</span><span class="sxs-lookup"><span data-stu-id="f01e9-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="f01e9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f01e9-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="f01e9-107">op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="f01e9-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="f01e9-108">Operace, která se má volat opakovaně</span><span class="sxs-lookup"><span data-stu-id="f01e9-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="f01e9-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f01e9-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f01e9-110">Počet vzorků volání `op` ke shromáždění.</span><span class="sxs-lookup"><span data-stu-id="f01e9-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="f01e9-111">vstup: ' TInput</span><span class="sxs-lookup"><span data-stu-id="f01e9-111">input : 'TInput</span></span>

<span data-ttu-id="f01e9-112">Vstup, který má být předán `op` .</span><span class="sxs-lookup"><span data-stu-id="f01e9-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="f01e9-113">Výstup: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="f01e9-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f01e9-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f01e9-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="f01e9-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="f01e9-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="f01e9-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="f01e9-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="f01e9-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="f01e9-117">See Also</span></span>

- [<span data-ttu-id="f01e9-118">Microsoft. v. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="f01e9-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)