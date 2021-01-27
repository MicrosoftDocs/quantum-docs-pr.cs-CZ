---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841049"
---
# <a name="boundc-function"></a><span data-ttu-id="a5205-102">BoundC – funkce</span><span class="sxs-lookup"><span data-stu-id="a5205-102">BoundC function</span></span>

<span data-ttu-id="a5205-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a5205-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a5205-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5205-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5205-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="a5205-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="a5205-106">Modifikátor `C` označuje, že všechny operace v poli jsou ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="a5205-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="a5205-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="a5205-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="a5205-108">operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je CTL []</span><span class="sxs-lookup"><span data-stu-id="a5205-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="a5205-109">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="a5205-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="a5205-110">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="a5205-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a5205-111">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="a5205-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a5205-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a5205-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5205-113">'S</span><span class="sxs-lookup"><span data-stu-id="a5205-113">'T</span></span>

<span data-ttu-id="a5205-114">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="a5205-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="a5205-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="a5205-115">Example</span></span>

<span data-ttu-id="a5205-116">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="a5205-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

<span data-ttu-id="a5205-117">a</span><span class="sxs-lookup"><span data-stu-id="a5205-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="a5205-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="a5205-118">See Also</span></span>

- [<span data-ttu-id="a5205-119">Microsoft. prodoby. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="a5205-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)