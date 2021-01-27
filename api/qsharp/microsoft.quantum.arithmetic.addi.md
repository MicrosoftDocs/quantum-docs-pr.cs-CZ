---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Operace AddI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: a17403652cc2b2712defe52112a3ac599330da9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843853"
---
# <a name="addi-operation"></a><span data-ttu-id="53551-102">Operace AddI</span><span class="sxs-lookup"><span data-stu-id="53551-102">AddI operation</span></span>

<span data-ttu-id="53551-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="53551-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="53551-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="53551-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="53551-105">Automaticky zvolí mezi doplněním a bez, v závislosti na velikosti registru `ys` .</span><span class="sxs-lookup"><span data-stu-id="53551-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="53551-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="53551-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="53551-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="53551-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="53551-108">$n sčítanec $-bit.</span><span class="sxs-lookup"><span data-stu-id="53551-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="53551-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="53551-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="53551-110">Sčítanec alespoň $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="53551-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="53551-111">Výsledek bude obsahovat.</span><span class="sxs-lookup"><span data-stu-id="53551-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53551-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53551-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

