---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698952"
---
# <a name="operationpow-function"></a><span data-ttu-id="ef58b-102">OperationPow – funkce</span><span class="sxs-lookup"><span data-stu-id="ef58b-102">OperationPow function</span></span>

<span data-ttu-id="ef58b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef58b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef58b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef58b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef58b-105">Vyvolá operaci s napájením.</span><span class="sxs-lookup"><span data-stu-id="ef58b-105">Raises an operation to a power.</span></span>

<span data-ttu-id="ef58b-106">To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.</span><span class="sxs-lookup"><span data-stu-id="ef58b-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="ef58b-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="ef58b-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ef58b-108">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef58b-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ef58b-109">Operace $U $ představuje bránu, která se má opakovat.</span><span class="sxs-lookup"><span data-stu-id="ef58b-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="ef58b-110">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ef58b-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ef58b-111">Počet opakování $U $.</span><span class="sxs-lookup"><span data-stu-id="ef58b-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="ef58b-112">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef58b-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ef58b-113">Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="ef58b-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ef58b-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ef58b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ef58b-115">'S</span><span class="sxs-lookup"><span data-stu-id="ef58b-115">'T</span></span>

<span data-ttu-id="ef58b-116">Typ operace, která má být zapnuta.</span><span class="sxs-lookup"><span data-stu-id="ef58b-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef58b-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="ef58b-117">See Also</span></span>

- [<span data-ttu-id="ef58b-118">Microsoft. proOperationPowC. Canon.</span><span class="sxs-lookup"><span data-stu-id="ef58b-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="ef58b-119">Microsoft. proOperationPowA. Canon.</span><span class="sxs-lookup"><span data-stu-id="ef58b-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="ef58b-120">Microsoft. proOperationPowCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="ef58b-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)