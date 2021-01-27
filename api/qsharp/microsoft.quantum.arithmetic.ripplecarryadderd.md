---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Operace RippleCarryAdderD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: f0f6f39fbff9f682f8f74a982c0a41847df1397a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842968"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="d7d78-102">Operace RippleCarryAdderD</span><span class="sxs-lookup"><span data-stu-id="d7d78-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="d7d78-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d7d78-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d7d78-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7d78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7d78-105">Vratný, místní Ripple – přidání dvou celých čísel.</span><span class="sxs-lookup"><span data-stu-id="d7d78-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="d7d78-106">Pomocí dvou $n $ bitových celých čísel zakódovaných v registrech LittleEndian `xs` a `ys` qubit, operace vypočítá součet dvou celých čísel, kde $n $ nejméně významné bity výsledku jsou uchovávány v `ys` a bit, který je XORed na qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="d7d78-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d7d78-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d7d78-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d7d78-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d7d78-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d7d78-109">LittleEndian qubit registruje kódování prvního celého čísla summand.</span><span class="sxs-lookup"><span data-stu-id="d7d78-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d7d78-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d7d78-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d7d78-111">LittleEndian qubit registruje kódování druhého celého čísla summand, je upraveno tak, aby obsahovalo $n $ nejméně významné bity součtu.</span><span class="sxs-lookup"><span data-stu-id="d7d78-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="d7d78-112">přenést: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d7d78-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d7d78-113">Přenese qubit, je XORed s nejvýznamnějším bitem součtu.</span><span class="sxs-lookup"><span data-stu-id="d7d78-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7d78-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7d78-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d7d78-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d7d78-115">Remarks</span></span>

<span data-ttu-id="d7d78-116">Určená řízená operace využívá symetrii a vzájemné rušení operací pro zlepšení výchozí implementace, která přidává ovládací prvek ke každé operaci.</span><span class="sxs-lookup"><span data-stu-id="d7d78-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="d7d78-117">Reference</span><span class="sxs-lookup"><span data-stu-id="d7d78-117">References</span></span>

- <span data-ttu-id="d7d78-118">Tomáš G. Draper: "Přihlaste se na počítač s více počítači a 2000.</span><span class="sxs-lookup"><span data-stu-id="d7d78-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033