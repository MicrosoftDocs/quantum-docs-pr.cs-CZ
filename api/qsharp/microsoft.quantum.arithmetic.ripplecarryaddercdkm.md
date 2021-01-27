---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Operace RippleCarryAdderCDKM
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: df9b62b649af532a4202aacc3e8dd4613eb8665d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846362"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="28892-102">Operace RippleCarryAdderCDKM</span><span class="sxs-lookup"><span data-stu-id="28892-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="28892-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="28892-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="28892-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28892-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28892-105">Vratný, místní Ripple – přidání dvou celých čísel.</span><span class="sxs-lookup"><span data-stu-id="28892-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="28892-106">Popis</span><span class="sxs-lookup"><span data-stu-id="28892-106">Description</span></span>

<span data-ttu-id="28892-107">Pomocí dvou $n $ bitových celých čísel zakódovaných v registrech LittleEndian `xs` a `ys` qubit, operace vypočítá součet dvou celých čísel, kde $n $ nejméně významné bity výsledku jsou uchovávány v `ys` a bit, který je XORed na qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="28892-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="28892-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="28892-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="28892-109">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="28892-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="28892-110">LittleEndian qubit registruje kódování prvního celého čísla summand.</span><span class="sxs-lookup"><span data-stu-id="28892-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="28892-111">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="28892-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="28892-112">LittleEndian qubit registruje kódování druhého celého čísla summand, je upraveno tak, aby obsahovalo n nejméně významné bity součtu.</span><span class="sxs-lookup"><span data-stu-id="28892-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="28892-113">přenést: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="28892-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="28892-114">Přenese qubit, je XORed s nejvýznamnějším bitem součtu.</span><span class="sxs-lookup"><span data-stu-id="28892-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28892-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28892-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="28892-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="28892-116">Remarks</span></span>

<span data-ttu-id="28892-117">Tato operace má stejné funkce jako RippleCarryAdderD, ale místo $n $ používá jenom jeden pomocný qubit.</span><span class="sxs-lookup"><span data-stu-id="28892-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="28892-118">Reference</span><span class="sxs-lookup"><span data-stu-id="28892-118">References</span></span>

- <span data-ttu-id="28892-119">Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton: "nové v rámci Ripple – přenést okruh", 2004.</span><span class="sxs-lookup"><span data-stu-id="28892-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1