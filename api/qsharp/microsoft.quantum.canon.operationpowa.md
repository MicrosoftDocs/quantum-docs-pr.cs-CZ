---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 67491c3302392e9793677727606df1baaf4f205a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852354"
---
# <a name="operationpowa-function"></a><span data-ttu-id="742d3-102">OperationPowA – funkce</span><span class="sxs-lookup"><span data-stu-id="742d3-102">OperationPowA function</span></span>

<span data-ttu-id="742d3-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="742d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="742d3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="742d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="742d3-105">Vyvolá operaci s napájením.</span><span class="sxs-lookup"><span data-stu-id="742d3-105">Raises an operation to a power.</span></span>
<span data-ttu-id="742d3-106">Modifikátor `A` označuje, že operace je sousední.</span><span class="sxs-lookup"><span data-stu-id="742d3-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="742d3-107">To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.</span><span class="sxs-lookup"><span data-stu-id="742d3-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="742d3-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="742d3-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="742d3-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="742d3-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="742d3-110">Operace $U $ představuje bránu, která se má opakovat.</span><span class="sxs-lookup"><span data-stu-id="742d3-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="742d3-111">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="742d3-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="742d3-112">Počet opakování $U $.</span><span class="sxs-lookup"><span data-stu-id="742d3-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="742d3-113">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="742d3-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="742d3-114">Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="742d3-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="742d3-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="742d3-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="742d3-116">'S</span><span class="sxs-lookup"><span data-stu-id="742d3-116">'T</span></span>

<span data-ttu-id="742d3-117">Typ operace, která má být zapnuta.</span><span class="sxs-lookup"><span data-stu-id="742d3-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="742d3-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="742d3-118">See Also</span></span>

- [<span data-ttu-id="742d3-119">Microsoft. proOperationPow. Canon.</span><span class="sxs-lookup"><span data-stu-id="742d3-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)