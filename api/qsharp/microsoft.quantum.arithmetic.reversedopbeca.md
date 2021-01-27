---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: ReversedOpBECA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 09bb99645d5946af0e0c654500165077691f8da3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846413"
---
# <a name="reversedopbeca-function"></a><span data-ttu-id="1e310-102">ReversedOpBECA – funkce</span><span class="sxs-lookup"><span data-stu-id="1e310-102">ReversedOpBECA function</span></span>

<span data-ttu-id="1e310-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1e310-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1e310-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e310-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e310-105">Vzhledem k operaci, která trvá vstupu big-endian, vrátí novou operaci, která bude mít vstup ze Little endian.</span><span class="sxs-lookup"><span data-stu-id="1e310-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="1e310-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="1e310-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="1e310-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="1e310-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1e310-108">Operace, jejíž vstup má být obrácený.</span><span class="sxs-lookup"><span data-stu-id="1e310-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="1e310-109">Výstup: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="1e310-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1e310-110">Nová operace, která přijme svůj vstup jako registr Little endian.</span><span class="sxs-lookup"><span data-stu-id="1e310-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e310-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="1e310-111">See Also</span></span>

- [<span data-ttu-id="1e310-112">Microsoft. prostředníky. aritmetické. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="1e310-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [<span data-ttu-id="1e310-113">Microsoft. prostředníky. aritmetické. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="1e310-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="1e310-114">Microsoft. prostředníky. aritmetické. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="1e310-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="1e310-115">Microsoft. prostředníky. aritmetické. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="1e310-115">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)