---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operace DrawMany
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706112"
---
# <a name="drawmany-operation"></a><span data-ttu-id="163fa-102">Operace DrawMany</span><span class="sxs-lookup"><span data-stu-id="163fa-102">DrawMany operation</span></span>

<span data-ttu-id="163fa-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="163fa-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="163fa-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="163fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="163fa-105">Opakuje operaci pro daný počet vzorků a shromažďuje jejich výstupy v poli.</span><span class="sxs-lookup"><span data-stu-id="163fa-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="163fa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="163fa-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="163fa-107">op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="163fa-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="163fa-108">Operace, která se má volat opakovaně</span><span class="sxs-lookup"><span data-stu-id="163fa-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="163fa-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="163fa-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="163fa-110">Počet vzorků volání `op` ke shromáždění.</span><span class="sxs-lookup"><span data-stu-id="163fa-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="163fa-111">vstup: ' TInput</span><span class="sxs-lookup"><span data-stu-id="163fa-111">input : 'TInput</span></span>

<span data-ttu-id="163fa-112">Vstup, který má být předán `op` .</span><span class="sxs-lookup"><span data-stu-id="163fa-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="163fa-113">Výstup: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="163fa-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="163fa-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="163fa-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="163fa-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="163fa-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="163fa-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="163fa-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="163fa-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="163fa-117">See Also</span></span>

- [<span data-ttu-id="163fa-118">Microsoft. v. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="163fa-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)