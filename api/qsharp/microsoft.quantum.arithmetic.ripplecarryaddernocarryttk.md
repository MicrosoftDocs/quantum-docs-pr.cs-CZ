---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: Operace RippleCarryAdderNoCarryTTK
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: a539d85a4800c2f4452a1c6fe2c4f88a6296c3e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221993"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="a8eb3-102">Operace RippleCarryAdderNoCarryTTK</span><span class="sxs-lookup"><span data-stu-id="a8eb3-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="a8eb3-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a8eb3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a8eb3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8eb3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8eb3-105">Vratný, místní Ripple – přidání dvou celých čísel bez nutnosti provádět.</span><span class="sxs-lookup"><span data-stu-id="a8eb3-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a8eb3-106">Popis</span><span class="sxs-lookup"><span data-stu-id="a8eb3-106">Description</span></span>

<span data-ttu-id="a8eb3-107">Tato dvě $nová celá čísla kódovaná v registrech LittleEndian `xs` a `ys` operace vypočítají součet dvou celých čísel modulo $2 ^ n $, kde $n $ je bitová velikost vstupů `xs` a `ys` .</span><span class="sxs-lookup"><span data-stu-id="a8eb3-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="a8eb3-108">Nepočítá se z něj bit provozování.</span><span class="sxs-lookup"><span data-stu-id="a8eb3-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="a8eb3-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="a8eb3-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a8eb3-110">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a8eb3-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a8eb3-111">LittleEndian qubit registruje kódování prvního celého čísla summand.</span><span class="sxs-lookup"><span data-stu-id="a8eb3-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="a8eb3-112">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a8eb3-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a8eb3-113">LittleEndian qubit registruje kódování druhého celého čísla summand, je upraveno tak, aby obsahovalo $n $ nejméně významné bity součtu.</span><span class="sxs-lookup"><span data-stu-id="a8eb3-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8eb3-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8eb3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a8eb3-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a8eb3-115">Remarks</span></span>

<span data-ttu-id="a8eb3-116">Tato operace má stejné funkce jako RippleCarryAdderTTK, ale nevrací bit přenosu.</span><span class="sxs-lookup"><span data-stu-id="a8eb3-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="a8eb3-117">Reference</span><span class="sxs-lookup"><span data-stu-id="a8eb3-117">References</span></span>

- <span data-ttu-id="a8eb3-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "dopředné a nevázané ventilátory, informace o všech procesorech a výpočet, obj. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="a8eb3-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530