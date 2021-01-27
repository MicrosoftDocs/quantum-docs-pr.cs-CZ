---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b0fcf1c735bb19308a381307e64314d9d961e5da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846435"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="5d7c8-102">ReversedOpLEA – funkce</span><span class="sxs-lookup"><span data-stu-id="5d7c8-102">ReversedOpLEA function</span></span>

<span data-ttu-id="5d7c8-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5d7c8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5d7c8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5d7c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5d7c8-105">Vzhledem k operaci, která trvá vstupu Little-endian, vrátí novou operaci, která bude mít vstup big-endian.</span><span class="sxs-lookup"><span data-stu-id="5d7c8-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="5d7c8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5d7c8-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="5d7c8-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ.</span><span class="sxs-lookup"><span data-stu-id="5d7c8-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5d7c8-108">Operace, jejíž vstup má být obrácený.</span><span class="sxs-lookup"><span data-stu-id="5d7c8-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj"></a><span data-ttu-id="5d7c8-109">Výstup: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je ADJ.</span><span class="sxs-lookup"><span data-stu-id="5d7c8-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5d7c8-110">Nová operace, která přijme svůj vstup jako registr big-endian.</span><span class="sxs-lookup"><span data-stu-id="5d7c8-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d7c8-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="5d7c8-111">See Also</span></span>

- [<span data-ttu-id="5d7c8-112">Microsoft. prostředníky. aritmetické. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="5d7c8-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="5d7c8-113">Microsoft. prostředníky. aritmetické. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="5d7c8-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="5d7c8-114">Microsoft. prostředníky. aritmetické. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="5d7c8-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="5d7c8-115">Microsoft. prostředníky. aritmetické. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="5d7c8-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)