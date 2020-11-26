---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operace Sum
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: 7758e29c9f08f4d05253defbe5a43a5316289522
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221789"
---
# <a name="sum-operation"></a><span data-ttu-id="ee9cb-102">Operace Sum</span><span class="sxs-lookup"><span data-stu-id="ee9cb-102">Sum operation</span></span>

<span data-ttu-id="ee9cb-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ee9cb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ee9cb-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee9cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee9cb-105">Implementuje bránu vratného součtu.</span><span class="sxs-lookup"><span data-stu-id="ee9cb-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="ee9cb-106">Má-li bit zakódovaný v qubit `carryIn` a dvě summand bity zakódované v `summand1` a `summand2` , vypočítá logickou XOR `carryIn` `summand1` a `summand2` v qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="ee9cb-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ee9cb-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="ee9cb-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="ee9cb-108">carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ee9cb-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ee9cb-109">Provádění qubit.</span><span class="sxs-lookup"><span data-stu-id="ee9cb-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="ee9cb-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ee9cb-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ee9cb-111">First summand qubit.</span><span class="sxs-lookup"><span data-stu-id="ee9cb-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="ee9cb-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ee9cb-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ee9cb-113">Druhý summand qubit je nahrazen nižším bitem součtu `summand1` a `summand2` .</span><span class="sxs-lookup"><span data-stu-id="ee9cb-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee9cb-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee9cb-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ee9cb-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ee9cb-115">Remarks</span></span>

<span data-ttu-id="ee9cb-116">Na rozdíl od `Carry` operace to nepočítá bit přenosu.</span><span class="sxs-lookup"><span data-stu-id="ee9cb-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>