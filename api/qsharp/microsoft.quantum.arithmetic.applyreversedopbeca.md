---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: Operace ApplyReversedOpBECA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 71e99d3390a2e510fd7ed28f3f6d8ed43b3ca7e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843567"
---
# <a name="applyreversedopbeca-operation"></a><span data-ttu-id="8950a-102">Operace ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="8950a-102">ApplyReversedOpBECA operation</span></span>

<span data-ttu-id="8950a-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8950a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8950a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8950a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8950a-105">Aplikuje operaci, která přebírá vstup big-endian do registru kódování unsigned integer ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="8950a-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8950a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8950a-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="8950a-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="8950a-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8950a-108">Operace, která funguje v registru big-endian.</span><span class="sxs-lookup"><span data-stu-id="8950a-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="8950a-109">registrovat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8950a-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8950a-110">Registr s malým endianm, který se má transformovat</span><span class="sxs-lookup"><span data-stu-id="8950a-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8950a-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8950a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8950a-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="8950a-112">See Also</span></span>

- [<span data-ttu-id="8950a-113">Microsoft. prostředníky. aritmetické. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="8950a-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="8950a-114">Microsoft. prostředníky. aritmetické. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="8950a-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="8950a-115">Microsoft. prostředníky. aritmetické. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="8950a-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)