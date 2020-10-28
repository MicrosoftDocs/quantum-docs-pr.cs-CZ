---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704465"
---
# <a name="bounda-function"></a><span data-ttu-id="62e7c-102">Bounda funkce</span><span class="sxs-lookup"><span data-stu-id="62e7c-102">BoundA function</span></span>

<span data-ttu-id="62e7c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="62e7c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="62e7c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62e7c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62e7c-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="62e7c-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="62e7c-106">Modifikátor `A` označuje, že všechny operace v poli jsou sousední.</span><span class="sxs-lookup"><span data-stu-id="62e7c-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="62e7c-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="62e7c-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="62e7c-108">operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ []</span><span class="sxs-lookup"><span data-stu-id="62e7c-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="62e7c-109">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="62e7c-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="62e7c-110">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="62e7c-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="62e7c-111">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="62e7c-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="62e7c-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="62e7c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="62e7c-113">'S</span><span class="sxs-lookup"><span data-stu-id="62e7c-113">'T</span></span>

<span data-ttu-id="62e7c-114">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="62e7c-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="62e7c-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="62e7c-115">See Also</span></span>

- [<span data-ttu-id="62e7c-116">Microsoft. prodoby. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="62e7c-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)