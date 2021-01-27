---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: Operace ApplyReversedOpBEA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1759764947cdbd84a1db945296d441a13f13767e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843584"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="4739e-102">Operace ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="4739e-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="4739e-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4739e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4739e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4739e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4739e-105">Aplikuje operaci, která přebírá vstup big-endian do registru kódování unsigned integer ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="4739e-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="4739e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4739e-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="4739e-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je ADJ.</span><span class="sxs-lookup"><span data-stu-id="4739e-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="4739e-108">Operace, která funguje v registru big-endian.</span><span class="sxs-lookup"><span data-stu-id="4739e-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="4739e-109">registrovat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4739e-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4739e-110">Registr s malým endianm, který se má transformovat</span><span class="sxs-lookup"><span data-stu-id="4739e-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4739e-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4739e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4739e-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="4739e-112">See Also</span></span>

- [<span data-ttu-id="4739e-113">Microsoft. prostředníky. aritmetické. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="4739e-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="4739e-114">Microsoft. prostředníky. aritmetické. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="4739e-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="4739e-115">Microsoft. prostředníky. aritmetické. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="4739e-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)