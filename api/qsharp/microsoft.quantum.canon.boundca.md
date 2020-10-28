---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704433"
---
# <a name="boundca-function"></a><span data-ttu-id="120cc-102">BoundCA – funkce</span><span class="sxs-lookup"><span data-stu-id="120cc-102">BoundCA function</span></span>

<span data-ttu-id="120cc-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="120cc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="120cc-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="120cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="120cc-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="120cc-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="120cc-106">Modifikátor `CA` označuje, že všechny operace v poli jsou sousedící a ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="120cc-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="120cc-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="120cc-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="120cc-108">operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="120cc-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="120cc-109">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="120cc-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="120cc-110">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="120cc-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="120cc-111">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="120cc-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="120cc-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="120cc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="120cc-113">'S</span><span class="sxs-lookup"><span data-stu-id="120cc-113">'T</span></span>

<span data-ttu-id="120cc-114">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="120cc-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="120cc-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="120cc-115">See Also</span></span>

- [<span data-ttu-id="120cc-116">Microsoft. prodoby. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="120cc-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)