---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 808001200d276ca21cc5a70140d5d84d96da3496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205809"
---
# <a name="operationpow-function"></a><span data-ttu-id="4fe11-102">OperationPow – funkce</span><span class="sxs-lookup"><span data-stu-id="4fe11-102">OperationPow function</span></span>

<span data-ttu-id="4fe11-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4fe11-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4fe11-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4fe11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4fe11-105">Vyvolá operaci s napájením.</span><span class="sxs-lookup"><span data-stu-id="4fe11-105">Raises an operation to a power.</span></span>

<span data-ttu-id="4fe11-106">To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.</span><span class="sxs-lookup"><span data-stu-id="4fe11-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="4fe11-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="4fe11-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4fe11-108">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fe11-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4fe11-109">Operace $U $ představuje bránu, která se má opakovat.</span><span class="sxs-lookup"><span data-stu-id="4fe11-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="4fe11-110">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4fe11-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4fe11-111">Počet opakování $U $.</span><span class="sxs-lookup"><span data-stu-id="4fe11-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="4fe11-112">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fe11-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4fe11-113">Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="4fe11-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4fe11-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4fe11-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4fe11-115">'S</span><span class="sxs-lookup"><span data-stu-id="4fe11-115">'T</span></span>

<span data-ttu-id="4fe11-116">Typ operace, která má být zapnuta.</span><span class="sxs-lookup"><span data-stu-id="4fe11-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fe11-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="4fe11-117">See Also</span></span>

- [<span data-ttu-id="4fe11-118">Microsoft. proOperationPowC. Canon.</span><span class="sxs-lookup"><span data-stu-id="4fe11-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="4fe11-119">Microsoft. proOperationPowA. Canon.</span><span class="sxs-lookup"><span data-stu-id="4fe11-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="4fe11-120">Microsoft. proOperationPowCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="4fe11-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)