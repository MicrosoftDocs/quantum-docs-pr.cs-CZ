---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844544"
---
# <a name="bounda-function"></a><span data-ttu-id="ba0c9-102">Bounda funkce</span><span class="sxs-lookup"><span data-stu-id="ba0c9-102">BoundA function</span></span>

<span data-ttu-id="ba0c9-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ba0c9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ba0c9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba0c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba0c9-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="ba0c9-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="ba0c9-106">Modifikátor `A` označuje, že všechny operace v poli jsou sousední.</span><span class="sxs-lookup"><span data-stu-id="ba0c9-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="ba0c9-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="ba0c9-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="ba0c9-108">operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ []</span><span class="sxs-lookup"><span data-stu-id="ba0c9-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="ba0c9-109">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="ba0c9-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="ba0c9-110">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="ba0c9-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ba0c9-111">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="ba0c9-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ba0c9-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ba0c9-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ba0c9-113">'S</span><span class="sxs-lookup"><span data-stu-id="ba0c9-113">'T</span></span>

<span data-ttu-id="ba0c9-114">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="ba0c9-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="ba0c9-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="ba0c9-115">Example</span></span>

<span data-ttu-id="ba0c9-116">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="ba0c9-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

<span data-ttu-id="ba0c9-117">a</span><span class="sxs-lookup"><span data-stu-id="ba0c9-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="ba0c9-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="ba0c9-118">See Also</span></span>

- [<span data-ttu-id="ba0c9-119">Microsoft. prodoby. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="ba0c9-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)