---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698928"
---
# <a name="operationpowc-function"></a><span data-ttu-id="c8fba-102">OperationPowC – funkce</span><span class="sxs-lookup"><span data-stu-id="c8fba-102">OperationPowC function</span></span>

<span data-ttu-id="c8fba-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c8fba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c8fba-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c8fba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c8fba-105">Vyvolá operaci s napájením.</span><span class="sxs-lookup"><span data-stu-id="c8fba-105">Raises an operation to a power.</span></span>
<span data-ttu-id="c8fba-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="c8fba-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="c8fba-107">To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.</span><span class="sxs-lookup"><span data-stu-id="c8fba-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c8fba-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="c8fba-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="c8fba-109">op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="c8fba-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c8fba-110">Operace $U $ představuje bránu, která se má opakovat.</span><span class="sxs-lookup"><span data-stu-id="c8fba-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="c8fba-111">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8fba-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8fba-112">Počet opakování $U $.</span><span class="sxs-lookup"><span data-stu-id="c8fba-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="c8fba-113">Výstup: t => seznam CTL pro [jednotku](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8fba-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c8fba-114">Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="c8fba-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c8fba-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c8fba-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c8fba-116">'S</span><span class="sxs-lookup"><span data-stu-id="c8fba-116">'T</span></span>

<span data-ttu-id="c8fba-117">Typ operace, která má být zapnuta.</span><span class="sxs-lookup"><span data-stu-id="c8fba-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8fba-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="c8fba-118">See Also</span></span>

- [<span data-ttu-id="c8fba-119">Microsoft. proOperationPow. Canon.</span><span class="sxs-lookup"><span data-stu-id="c8fba-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)