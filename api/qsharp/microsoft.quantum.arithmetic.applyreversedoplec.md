---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: Operace ApplyReversedOpLEC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 75b6c0f09c0699b50d9ac1b0274e8074520fc241
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202647"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="515d5-102">Operace ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="515d5-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="515d5-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="515d5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="515d5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="515d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="515d5-105">Aplikuje operaci, která se zařadí do registru pomocí formátu Little endian, a kódování unsigned integer ve formátu big endian.</span><span class="sxs-lookup"><span data-stu-id="515d5-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="515d5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="515d5-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="515d5-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je CTL</span><span class="sxs-lookup"><span data-stu-id="515d5-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="515d5-108">Operace, která funguje v registru Little-endian.</span><span class="sxs-lookup"><span data-stu-id="515d5-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="515d5-109">registrovat: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="515d5-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="515d5-110">Registr big-endian, který se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="515d5-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="515d5-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="515d5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="515d5-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="515d5-112">See Also</span></span>

- [<span data-ttu-id="515d5-113">Microsoft. prostředníky. aritmetické. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="515d5-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="515d5-114">Microsoft. prostředníky. aritmetické. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="515d5-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="515d5-115">Microsoft. prostředníky. aritmetické. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="515d5-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)