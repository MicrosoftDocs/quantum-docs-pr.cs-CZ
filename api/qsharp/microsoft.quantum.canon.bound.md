---
uid: Microsoft.Quantum.Canon.Bound
title: Vázaná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841051"
---
# <a name="bound-function"></a><span data-ttu-id="06806-102">Vázaná funkce</span><span class="sxs-lookup"><span data-stu-id="06806-102">Bound function</span></span>

<span data-ttu-id="06806-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="06806-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="06806-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06806-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06806-105">Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.</span><span class="sxs-lookup"><span data-stu-id="06806-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="06806-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="06806-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="06806-107">operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="06806-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="06806-108">Posloupnost operací, které mají být provedeny na daném vstupu.</span><span class="sxs-lookup"><span data-stu-id="06806-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="06806-109">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06806-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="06806-110">Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.</span><span class="sxs-lookup"><span data-stu-id="06806-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="06806-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="06806-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="06806-112">'S</span><span class="sxs-lookup"><span data-stu-id="06806-112">'T</span></span>

<span data-ttu-id="06806-113">Cíl, na kterém každá z operací v poli působí.</span><span class="sxs-lookup"><span data-stu-id="06806-113">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="06806-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="06806-114">Example</span></span>

<span data-ttu-id="06806-115">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="06806-115">The following are equivalent:</span></span>

```qsharp
let bound = Bound([U, V]);
bound(x);
```

<span data-ttu-id="06806-116">a</span><span class="sxs-lookup"><span data-stu-id="06806-116">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="06806-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="06806-117">See Also</span></span>

- [<span data-ttu-id="06806-118">Microsoft. proBoundC. Canon.</span><span class="sxs-lookup"><span data-stu-id="06806-118">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="06806-119">Microsoft. prodoby. Canon. Bound.</span><span class="sxs-lookup"><span data-stu-id="06806-119">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="06806-120">Microsoft. proBoundCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="06806-120">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)