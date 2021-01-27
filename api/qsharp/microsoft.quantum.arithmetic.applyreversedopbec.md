---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: Operace ApplyReversedOpBEC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 7d118d1b04c37a80e61dfab2ee2265b3596b5877
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843563"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="99eb9-102">Operace ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="99eb9-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="99eb9-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="99eb9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="99eb9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99eb9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99eb9-105">Aplikuje operaci, která přebírá vstup big-endian do registru kódování unsigned integer ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="99eb9-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="99eb9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="99eb9-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="99eb9-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je CTL</span><span class="sxs-lookup"><span data-stu-id="99eb9-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="99eb9-108">Operace, která funguje v registru big-endian.</span><span class="sxs-lookup"><span data-stu-id="99eb9-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="99eb9-109">registrovat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="99eb9-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="99eb9-110">Registr s malým endianm, který se má transformovat</span><span class="sxs-lookup"><span data-stu-id="99eb9-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99eb9-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99eb9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="99eb9-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="99eb9-112">See Also</span></span>

- [<span data-ttu-id="99eb9-113">Microsoft. prostředníky. aritmetické. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="99eb9-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="99eb9-114">Microsoft. prostředníky. aritmetické. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="99eb9-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="99eb9-115">Microsoft. prostředníky. aritmetické. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="99eb9-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)