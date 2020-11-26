---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operace IncrementByInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fa5e75e91206aa5f33233c8a54d6e9e7ac2950e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222962"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="fed18-102">Operace IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="fed18-102">IncrementByInteger operation</span></span>

<span data-ttu-id="fed18-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fed18-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fed18-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fed18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fed18-105">Zvýší nepodepsaná bezplatných hodnot do registru pomocí klasického celého čísla pomocí otočení fáze.</span><span class="sxs-lookup"><span data-stu-id="fed18-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="fed18-106">Popis</span><span class="sxs-lookup"><span data-stu-id="fed18-106">Description</span></span>

<span data-ttu-id="fed18-107">Předpokládejme, že `target` kódování unsigned integer $x $ v kódování Little endian a `increment` je rovno $a $.</span><span class="sxs-lookup"><span data-stu-id="fed18-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="fed18-108">Tato operace pak implementuje jednotkové $ \ket{x} \mapsto \ket{x + a} $, kde sčítání se provádí modulo $2 ^ n $, kde $n = \texttt{Length (Target!)} $.</span><span class="sxs-lookup"><span data-stu-id="fed18-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="fed18-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="fed18-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="fed18-110">přírůstek: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fed18-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fed18-111">Celé číslo, kterým `target` se zvyšuje hodnota.</span><span class="sxs-lookup"><span data-stu-id="fed18-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="fed18-112">cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fed18-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fed18-113">V případě, že dojde k zaregistrování kódování unsigned integer pomocí kódování Little endian.</span><span class="sxs-lookup"><span data-stu-id="fed18-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fed18-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fed18-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

