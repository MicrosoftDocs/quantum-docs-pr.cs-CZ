---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698924"
---
# <a name="operationpowca-function"></a><span data-ttu-id="45015-102">OperationPowCA – funkce</span><span class="sxs-lookup"><span data-stu-id="45015-102">OperationPowCA function</span></span>

<span data-ttu-id="45015-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45015-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45015-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45015-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45015-105">Vyvolá operaci s napájením.</span><span class="sxs-lookup"><span data-stu-id="45015-105">Raises an operation to a power.</span></span>
<span data-ttu-id="45015-106">Modifikátor `A` označuje, že operace je ovladatelné a s sousedními poli.</span><span class="sxs-lookup"><span data-stu-id="45015-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="45015-107">To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.</span><span class="sxs-lookup"><span data-stu-id="45015-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="45015-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="45015-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="45015-109">op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ</span><span class="sxs-lookup"><span data-stu-id="45015-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="45015-110">Operace $U $ představuje bránu, která se má opakovat.</span><span class="sxs-lookup"><span data-stu-id="45015-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="45015-111">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="45015-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="45015-112">Počet opakování $U $.</span><span class="sxs-lookup"><span data-stu-id="45015-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl--adj"></a><span data-ttu-id="45015-113">Výstup: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ</span><span class="sxs-lookup"><span data-stu-id="45015-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="45015-114">Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="45015-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="45015-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="45015-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45015-116">'S</span><span class="sxs-lookup"><span data-stu-id="45015-116">'T</span></span>

<span data-ttu-id="45015-117">Typ operace, která má být zapnuta.</span><span class="sxs-lookup"><span data-stu-id="45015-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="45015-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="45015-118">See Also</span></span>

- [<span data-ttu-id="45015-119">Microsoft. proOperationPow. Canon.</span><span class="sxs-lookup"><span data-stu-id="45015-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)