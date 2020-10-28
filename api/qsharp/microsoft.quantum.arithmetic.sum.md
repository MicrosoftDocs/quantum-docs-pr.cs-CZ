---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operace Sum
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706200"
---
# <a name="sum-operation"></a><span data-ttu-id="84899-102">Operace Sum</span><span class="sxs-lookup"><span data-stu-id="84899-102">Sum operation</span></span>

<span data-ttu-id="84899-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="84899-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="84899-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84899-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84899-105">Implementuje bránu vratného součtu.</span><span class="sxs-lookup"><span data-stu-id="84899-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="84899-106">Má-li bit zakódovaný v qubit `carryIn` a dvě summand bity zakódované v `summand1` a `summand2` , vypočítá logickou XOR `carryIn` `summand1` a `summand2` v qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="84899-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="84899-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="84899-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="84899-108">carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="84899-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="84899-109">Provádění qubit.</span><span class="sxs-lookup"><span data-stu-id="84899-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="84899-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="84899-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="84899-111">First summand qubit.</span><span class="sxs-lookup"><span data-stu-id="84899-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="84899-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="84899-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="84899-113">Druhý summand qubit je nahrazen nižším bitem součtu `summand1` a `summand2` .</span><span class="sxs-lookup"><span data-stu-id="84899-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84899-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84899-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="84899-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="84899-115">Remarks</span></span>

<span data-ttu-id="84899-116">Na rozdíl od `Carry` operace to nepočítá bit přenosu.</span><span class="sxs-lookup"><span data-stu-id="84899-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>