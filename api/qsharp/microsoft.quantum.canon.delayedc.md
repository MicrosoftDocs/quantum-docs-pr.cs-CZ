---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704193"
---
# <a name="delayedc-function"></a><span data-ttu-id="14a3d-102">DelayedC – funkce</span><span class="sxs-lookup"><span data-stu-id="14a3d-102">DelayedC function</span></span>

<span data-ttu-id="14a3d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14a3d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14a3d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14a3d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14a3d-105">Vrátí operaci, která aplikuje danou operaci s daným argumentem.</span><span class="sxs-lookup"><span data-stu-id="14a3d-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="14a3d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="14a3d-106">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="14a3d-107">op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="14a3d-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="14a3d-108">Operace, která se má použít v důsledku použití návratové hodnoty</span><span class="sxs-lookup"><span data-stu-id="14a3d-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="14a3d-109">ARG: t</span><span class="sxs-lookup"><span data-stu-id="14a3d-109">arg : 'T</span></span>

<span data-ttu-id="14a3d-110">Vstup, na který se operace `op` používá</span><span class="sxs-lookup"><span data-stu-id="14a3d-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl"></a><span data-ttu-id="14a3d-111">Výstup: [jednotky](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL v jednotce</span><span class="sxs-lookup"><span data-stu-id="14a3d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="14a3d-112">Nová operace, která se vztahuje na `op` vstup `arg`</span><span class="sxs-lookup"><span data-stu-id="14a3d-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="14a3d-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="14a3d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="14a3d-114">'S</span><span class="sxs-lookup"><span data-stu-id="14a3d-114">'T</span></span>

<span data-ttu-id="14a3d-115">Vstupní typ operace, která se má zpozdit</span><span class="sxs-lookup"><span data-stu-id="14a3d-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="14a3d-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="14a3d-116">See Also</span></span>

- [<span data-ttu-id="14a3d-117">Microsoft. prodoby. Canon. zpoždění</span><span class="sxs-lookup"><span data-stu-id="14a3d-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="14a3d-118">Microsoft... Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="14a3d-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)