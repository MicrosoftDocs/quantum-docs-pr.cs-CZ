---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704456"
---
# <a name="boundc-function"></a><span data-ttu-id="3efc1-102">BoundC – funkce</span><span class="sxs-lookup"><span data-stu-id="3efc1-102">BoundC function</span></span>

<span data-ttu-id="3efc1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3efc1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3efc1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3efc1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3efc1-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="3efc1-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="3efc1-106">Modifikátor `C` označuje, že všechny operace v poli jsou ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="3efc1-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="3efc1-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="3efc1-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="3efc1-108">operace: t [=> CTL](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="3efc1-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="3efc1-109">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="3efc1-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="3efc1-110">Výstup: t => seznam CTL pro [jednotku](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3efc1-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="3efc1-111">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="3efc1-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3efc1-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3efc1-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3efc1-113">'S</span><span class="sxs-lookup"><span data-stu-id="3efc1-113">'T</span></span>

<span data-ttu-id="3efc1-114">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="3efc1-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="3efc1-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="3efc1-115">See Also</span></span>

- [<span data-ttu-id="3efc1-116">Microsoft. prodoby. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="3efc1-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)