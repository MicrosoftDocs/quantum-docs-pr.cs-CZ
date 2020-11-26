---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 32de77cbd54cc8eeb8c4a967fd046dca709cd9ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205639"
---
# <a name="operationpowca-function"></a><span data-ttu-id="12620-102">OperationPowCA – funkce</span><span class="sxs-lookup"><span data-stu-id="12620-102">OperationPowCA function</span></span>

<span data-ttu-id="12620-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="12620-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="12620-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12620-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12620-105">Vyvolá operaci s napájením.</span><span class="sxs-lookup"><span data-stu-id="12620-105">Raises an operation to a power.</span></span>
<span data-ttu-id="12620-106">Modifikátor `A` označuje, že operace je ovladatelné a s sousedními poli.</span><span class="sxs-lookup"><span data-stu-id="12620-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="12620-107">To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.</span><span class="sxs-lookup"><span data-stu-id="12620-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="12620-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="12620-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="12620-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="12620-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="12620-110">Operace $U $ představuje bránu, která se má opakovat.</span><span class="sxs-lookup"><span data-stu-id="12620-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="12620-111">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12620-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12620-112">Počet opakování $U $.</span><span class="sxs-lookup"><span data-stu-id="12620-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="12620-113">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="12620-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="12620-114">Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="12620-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="12620-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="12620-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="12620-116">'S</span><span class="sxs-lookup"><span data-stu-id="12620-116">'T</span></span>

<span data-ttu-id="12620-117">Typ operace, která má být zapnuta.</span><span class="sxs-lookup"><span data-stu-id="12620-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="12620-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="12620-118">See Also</span></span>

- [<span data-ttu-id="12620-119">Microsoft. proOperationPow. Canon.</span><span class="sxs-lookup"><span data-stu-id="12620-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)