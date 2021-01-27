---
uid: Microsoft.Quantum.Canon.DelayedA
title: Opožděná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: e53279bd3ddc5fa8bc0c862f998b273a9e17a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840604"
---
# <a name="delayeda-function"></a><span data-ttu-id="ad46b-102">Opožděná funkce</span><span class="sxs-lookup"><span data-stu-id="ad46b-102">DelayedA function</span></span>

<span data-ttu-id="ad46b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ad46b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ad46b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad46b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad46b-105">Vrátí operaci, která aplikuje danou operaci s daným argumentem.</span><span class="sxs-lookup"><span data-stu-id="ad46b-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="ad46b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ad46b-106">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="ad46b-107">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="ad46b-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ad46b-108">Operace, která se má použít v důsledku použití návratové hodnoty</span><span class="sxs-lookup"><span data-stu-id="ad46b-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="ad46b-109">ARG: t</span><span class="sxs-lookup"><span data-stu-id="ad46b-109">arg : 'T</span></span>

<span data-ttu-id="ad46b-110">Vstup, na který se operace `op` používá</span><span class="sxs-lookup"><span data-stu-id="ad46b-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj"></a><span data-ttu-id="ad46b-111">Výstup: jednotka [jednotky](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) je ADJ.</span><span class="sxs-lookup"><span data-stu-id="ad46b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ad46b-112">Nová operace, která se vztahuje na `op` vstup `arg`</span><span class="sxs-lookup"><span data-stu-id="ad46b-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ad46b-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ad46b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad46b-114">'S</span><span class="sxs-lookup"><span data-stu-id="ad46b-114">'T</span></span>

<span data-ttu-id="ad46b-115">Vstupní typ operace, která se má zpozdit</span><span class="sxs-lookup"><span data-stu-id="ad46b-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad46b-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="ad46b-116">See Also</span></span>

- [<span data-ttu-id="ad46b-117">Microsoft. prodoby. Canon. zpoždění</span><span class="sxs-lookup"><span data-stu-id="ad46b-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="ad46b-118">Microsoft... Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="ad46b-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)