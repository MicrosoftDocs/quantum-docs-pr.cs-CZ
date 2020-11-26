---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207577"
---
# <a name="boundc-function"></a><span data-ttu-id="ebc96-102">BoundC – funkce</span><span class="sxs-lookup"><span data-stu-id="ebc96-102">BoundC function</span></span>

<span data-ttu-id="ebc96-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ebc96-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ebc96-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebc96-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebc96-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="ebc96-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="ebc96-106">Modifikátor `C` označuje, že všechny operace v poli jsou ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="ebc96-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="ebc96-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="ebc96-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="ebc96-108">operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je CTL []</span><span class="sxs-lookup"><span data-stu-id="ebc96-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="ebc96-109">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="ebc96-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="ebc96-110">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="ebc96-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ebc96-111">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="ebc96-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ebc96-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ebc96-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ebc96-113">'S</span><span class="sxs-lookup"><span data-stu-id="ebc96-113">'T</span></span>

<span data-ttu-id="ebc96-114">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="ebc96-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebc96-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="ebc96-115">See Also</span></span>

- [<span data-ttu-id="ebc96-116">Microsoft. prodoby. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="ebc96-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)