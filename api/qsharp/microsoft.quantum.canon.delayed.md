---
uid: Microsoft.Quantum.Canon.Delayed
title: Opožděná funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704217"
---
# <a name="delayed-function"></a><span data-ttu-id="89e25-102">Opožděná funkce</span><span class="sxs-lookup"><span data-stu-id="89e25-102">Delayed function</span></span>

<span data-ttu-id="89e25-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="89e25-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="89e25-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89e25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89e25-105">Vrátí operaci, která aplikuje danou operaci s daným argumentem.</span><span class="sxs-lookup"><span data-stu-id="89e25-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="89e25-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="89e25-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="89e25-107">op: t => ' U</span><span class="sxs-lookup"><span data-stu-id="89e25-107">op : 'T => 'U</span></span> 

<span data-ttu-id="89e25-108">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="89e25-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="89e25-109">ARG: t</span><span class="sxs-lookup"><span data-stu-id="89e25-109">arg : 'T</span></span>

<span data-ttu-id="89e25-110">Vstup, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="89e25-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="89e25-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="89e25-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="89e25-112">Nová operace, která se vztahuje na `op` vstup `arg`</span><span class="sxs-lookup"><span data-stu-id="89e25-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="89e25-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="89e25-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="89e25-114">'S</span><span class="sxs-lookup"><span data-stu-id="89e25-114">'T</span></span>

<span data-ttu-id="89e25-115">Vstupní typ operace, která se má zpozdit</span><span class="sxs-lookup"><span data-stu-id="89e25-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="89e25-116">U</span><span class="sxs-lookup"><span data-stu-id="89e25-116">'U</span></span>

<span data-ttu-id="89e25-117">Návratový typ operace, která se má zpozdit.</span><span class="sxs-lookup"><span data-stu-id="89e25-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="89e25-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="89e25-118">See Also</span></span>

- [<span data-ttu-id="89e25-119">Microsoft. proDelayedC. Canon.</span><span class="sxs-lookup"><span data-stu-id="89e25-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="89e25-120">Microsoft. prodoby. Canon. zpoždění</span><span class="sxs-lookup"><span data-stu-id="89e25-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="89e25-121">Microsoft. proDelayedCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="89e25-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="89e25-122">Microsoft... Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="89e25-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)