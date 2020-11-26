---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: Operace ApplyReversedOpBE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 6db1fcb7437d97b1e56c64165d1be523ed2df07a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202851"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="2e521-102">Operace ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="2e521-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="2e521-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2e521-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2e521-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e521-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e521-105">Aplikuje operaci, která přebírá vstup big-endian do registru kódování unsigned integer ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="2e521-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="2e521-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2e521-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="2e521-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="2e521-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2e521-108">Operace, která funguje v registru big-endian.</span><span class="sxs-lookup"><span data-stu-id="2e521-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="2e521-109">registrovat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2e521-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2e521-110">Registr s malým endianm, který se má transformovat</span><span class="sxs-lookup"><span data-stu-id="2e521-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e521-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e521-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2e521-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="2e521-112">See Also</span></span>

- [<span data-ttu-id="2e521-113">Microsoft. prostředníky. aritmetické. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="2e521-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="2e521-114">Microsoft. prostředníky. aritmetické. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="2e521-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="2e521-115">Microsoft. prostředníky. aritmetické. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="2e521-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)