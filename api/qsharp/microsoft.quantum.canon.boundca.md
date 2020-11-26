---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216876"
---
# <a name="boundca-function"></a><span data-ttu-id="e983a-102">BoundCA – funkce</span><span class="sxs-lookup"><span data-stu-id="e983a-102">BoundCA function</span></span>

<span data-ttu-id="e983a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e983a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e983a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e983a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e983a-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="e983a-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="e983a-106">Modifikátor `CA` označuje, že všechny operace v poli jsou sousedící a ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="e983a-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e983a-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="e983a-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="e983a-108">operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="e983a-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="e983a-109">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="e983a-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="e983a-110">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="e983a-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e983a-111">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="e983a-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e983a-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e983a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e983a-113">'S</span><span class="sxs-lookup"><span data-stu-id="e983a-113">'T</span></span>

<span data-ttu-id="e983a-114">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="e983a-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="e983a-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="e983a-115">See Also</span></span>

- [<span data-ttu-id="e983a-116">Microsoft. prodoby. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="e983a-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)