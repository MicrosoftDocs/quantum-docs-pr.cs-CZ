---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operace Sum
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847753"
---
# <a name="sum-operation"></a><span data-ttu-id="8015d-102">Operace Sum</span><span class="sxs-lookup"><span data-stu-id="8015d-102">Sum operation</span></span>

<span data-ttu-id="8015d-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8015d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8015d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8015d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8015d-105">Implementuje bránu vratného součtu.</span><span class="sxs-lookup"><span data-stu-id="8015d-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="8015d-106">Má-li bit zakódovaný v qubit `carryIn` a dvě summand bity zakódované v `summand1` a `summand2` , vypočítá logickou XOR `carryIn` `summand1` a `summand2` v qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="8015d-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8015d-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="8015d-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="8015d-108">carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8015d-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8015d-109">Provádění qubit.</span><span class="sxs-lookup"><span data-stu-id="8015d-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="8015d-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8015d-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8015d-111">First summand qubit.</span><span class="sxs-lookup"><span data-stu-id="8015d-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="8015d-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8015d-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8015d-113">Druhý summand qubit je nahrazen nižším bitem součtu `summand1` a `summand2` .</span><span class="sxs-lookup"><span data-stu-id="8015d-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8015d-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8015d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8015d-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8015d-115">Remarks</span></span>

<span data-ttu-id="8015d-116">Na rozdíl od `Carry` operace to nepočítá bit přenosu.</span><span class="sxs-lookup"><span data-stu-id="8015d-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>