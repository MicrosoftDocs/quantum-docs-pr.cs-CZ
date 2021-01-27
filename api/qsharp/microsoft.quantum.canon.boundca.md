---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844518"
---
# <a name="boundca-function"></a><span data-ttu-id="9a97e-102">BoundCA – funkce</span><span class="sxs-lookup"><span data-stu-id="9a97e-102">BoundCA function</span></span>

<span data-ttu-id="9a97e-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a97e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a97e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a97e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a97e-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="9a97e-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="9a97e-106">Modifikátor `CA` označuje, že všechny operace v poli jsou sousedící a ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="9a97e-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9a97e-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="9a97e-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="9a97e-108">operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="9a97e-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="9a97e-109">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="9a97e-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="9a97e-110">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="9a97e-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9a97e-111">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="9a97e-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9a97e-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9a97e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a97e-113">'S</span><span class="sxs-lookup"><span data-stu-id="9a97e-113">'T</span></span>

<span data-ttu-id="9a97e-114">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="9a97e-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="9a97e-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="9a97e-115">Example</span></span>

<span data-ttu-id="9a97e-116">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="9a97e-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="9a97e-117">a</span><span class="sxs-lookup"><span data-stu-id="9a97e-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="9a97e-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="9a97e-118">See Also</span></span>

- [<span data-ttu-id="9a97e-119">Microsoft. prodoby. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="9a97e-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)