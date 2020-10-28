---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Provozovaná operace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 2b977151861fb01be7d7dbad6e0a7b803fded880
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707401"
---
# <a name="carry-operation"></a><span data-ttu-id="aade3-102">Provozovaná operace</span><span class="sxs-lookup"><span data-stu-id="aade3-102">Carry operation</span></span>

<span data-ttu-id="aade3-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aade3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aade3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aade3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aade3-105">Implementuje bránu vratného přenosu.</span><span class="sxs-lookup"><span data-stu-id="aade3-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="aade3-106">S ohledem na zakódovaný bit v qubit `carryIn` a dvou summand bitů kódovaný v `summand1` a `summand2` , vypočítá logickou XOR `carryIn` , `summand1` a `summand2` v qubit `summand2` a přenese XORed na qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="aade3-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="aade3-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="aade3-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="aade3-108">carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aade3-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aade3-109">Provádění qubit.</span><span class="sxs-lookup"><span data-stu-id="aade3-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="aade3-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aade3-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aade3-111">First summand qubit.</span><span class="sxs-lookup"><span data-stu-id="aade3-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="aade3-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aade3-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aade3-113">Druhý summand qubit je nahrazen nižším bitem součtu `summand1` a `summand2` .</span><span class="sxs-lookup"><span data-stu-id="aade3-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="aade3-114">vykonání: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aade3-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aade3-115">Qubit se bude XORed s vyšším bitem součtu.</span><span class="sxs-lookup"><span data-stu-id="aade3-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aade3-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aade3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

