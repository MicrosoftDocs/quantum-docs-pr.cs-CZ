---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: fe2babb87d716185286b0864745f7ff6e637f8a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207001"
---
# <a name="delayedca-function"></a><span data-ttu-id="9ed02-102">DelayedCA – funkce</span><span class="sxs-lookup"><span data-stu-id="9ed02-102">DelayedCA function</span></span>

<span data-ttu-id="9ed02-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ed02-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ed02-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ed02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ed02-105">Vrátí operaci, která aplikuje danou operaci s daným argumentem.</span><span class="sxs-lookup"><span data-stu-id="9ed02-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="9ed02-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9ed02-106">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="9ed02-107">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="9ed02-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9ed02-108">Operace, která se má použít v důsledku použití návratové hodnoty</span><span class="sxs-lookup"><span data-stu-id="9ed02-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="9ed02-109">ARG: t</span><span class="sxs-lookup"><span data-stu-id="9ed02-109">arg : 'T</span></span>

<span data-ttu-id="9ed02-110">Vstup, na který se operace `op` používá</span><span class="sxs-lookup"><span data-stu-id="9ed02-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj--ctl"></a><span data-ttu-id="9ed02-111">Výstup: [jednotka jednotky](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="9ed02-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9ed02-112">Nová operace, která se vztahuje na `op` vstup `arg`</span><span class="sxs-lookup"><span data-stu-id="9ed02-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9ed02-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9ed02-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ed02-114">'S</span><span class="sxs-lookup"><span data-stu-id="9ed02-114">'T</span></span>

<span data-ttu-id="9ed02-115">Vstupní typ operace, která se má zpozdit</span><span class="sxs-lookup"><span data-stu-id="9ed02-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ed02-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="9ed02-116">See Also</span></span>

- [<span data-ttu-id="9ed02-117">Microsoft. prodoby. Canon. zpoždění</span><span class="sxs-lookup"><span data-stu-id="9ed02-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="9ed02-118">Microsoft... Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="9ed02-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)