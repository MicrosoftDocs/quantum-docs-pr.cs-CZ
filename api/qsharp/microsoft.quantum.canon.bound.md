---
uid: Microsoft.Quantum.Canon.Bound
title: Vázaná funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207594"
---
# <a name="bound-function"></a><span data-ttu-id="f4dde-102">Vázaná funkce</span><span class="sxs-lookup"><span data-stu-id="f4dde-102">Bound function</span></span>

<span data-ttu-id="f4dde-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4dde-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4dde-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4dde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4dde-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="f4dde-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="f4dde-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f4dde-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="f4dde-107">operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="f4dde-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="f4dde-108">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="f4dde-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="f4dde-109">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4dde-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f4dde-110">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="f4dde-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f4dde-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f4dde-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4dde-112">'S</span><span class="sxs-lookup"><span data-stu-id="f4dde-112">'T</span></span>

<span data-ttu-id="f4dde-113">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="f4dde-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4dde-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="f4dde-114">See Also</span></span>

- [<span data-ttu-id="f4dde-115">Microsoft. proBoundC. Canon.</span><span class="sxs-lookup"><span data-stu-id="f4dde-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="f4dde-116">Microsoft. prodoby. Canon. Bound.</span><span class="sxs-lookup"><span data-stu-id="f4dde-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="f4dde-117">Microsoft. proBoundCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f4dde-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)