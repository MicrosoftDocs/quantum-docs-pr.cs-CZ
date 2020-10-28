---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698936"
---
# <a name="operationpowa-function"></a><span data-ttu-id="834b6-102">OperationPowA – funkce</span><span class="sxs-lookup"><span data-stu-id="834b6-102">OperationPowA function</span></span>

<span data-ttu-id="834b6-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="834b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="834b6-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="834b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="834b6-105">Vyvolá operaci s napájením.</span><span class="sxs-lookup"><span data-stu-id="834b6-105">Raises an operation to a power.</span></span>
<span data-ttu-id="834b6-106">Modifikátor `A` označuje, že operace je sousední.</span><span class="sxs-lookup"><span data-stu-id="834b6-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="834b6-107">To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.</span><span class="sxs-lookup"><span data-stu-id="834b6-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="834b6-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="834b6-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="834b6-109">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="834b6-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="834b6-110">Operace $U $ představuje bránu, která se má opakovat.</span><span class="sxs-lookup"><span data-stu-id="834b6-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="834b6-111">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="834b6-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="834b6-112">Počet opakování $U $.</span><span class="sxs-lookup"><span data-stu-id="834b6-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="834b6-113">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="834b6-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="834b6-114">Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="834b6-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="834b6-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="834b6-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="834b6-116">'S</span><span class="sxs-lookup"><span data-stu-id="834b6-116">'T</span></span>

<span data-ttu-id="834b6-117">Typ operace, která má být zapnuta.</span><span class="sxs-lookup"><span data-stu-id="834b6-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="834b6-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="834b6-118">See Also</span></span>

- [<span data-ttu-id="834b6-119">Microsoft. proOperationPow. Canon.</span><span class="sxs-lookup"><span data-stu-id="834b6-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)