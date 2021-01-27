---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d4245437f2b71abb8bf1bbe4db43ae7d2ee23799
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845756"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="4402c-102">ReversedOpLECA – funkce</span><span class="sxs-lookup"><span data-stu-id="4402c-102">ReversedOpLECA function</span></span>

<span data-ttu-id="4402c-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4402c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4402c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4402c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4402c-105">Vzhledem k operaci, která trvá vstupu Little-endian, vrátí novou operaci, která bude mít vstup big-endian.</span><span class="sxs-lookup"><span data-stu-id="4402c-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4402c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4402c-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="4402c-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="4402c-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4402c-108">Operace, jejíž vstup má být obrácený.</span><span class="sxs-lookup"><span data-stu-id="4402c-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="4402c-109">Výstup: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="4402c-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4402c-110">Nová operace, která přijme svůj vstup jako registr big-endian.</span><span class="sxs-lookup"><span data-stu-id="4402c-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="4402c-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="4402c-111">See Also</span></span>

- [<span data-ttu-id="4402c-112">Microsoft. prostředníky. aritmetické. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="4402c-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="4402c-113">Microsoft. prostředníky. aritmetické. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="4402c-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="4402c-114">Microsoft. prostředníky. aritmetické. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="4402c-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="4402c-115">Microsoft. prostředníky. aritmetické. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="4402c-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)