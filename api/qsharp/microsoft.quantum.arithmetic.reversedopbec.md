---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 0674567f5d45890aa2f631b2e0e4d75d20a72449
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846439"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="7a271-102">ReversedOpBEC – funkce</span><span class="sxs-lookup"><span data-stu-id="7a271-102">ReversedOpBEC function</span></span>

<span data-ttu-id="7a271-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7a271-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7a271-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a271-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a271-105">Vzhledem k operaci, která trvá vstupu big-endian, vrátí novou operaci, která bude mít vstup ze Little endian.</span><span class="sxs-lookup"><span data-stu-id="7a271-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="7a271-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7a271-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="7a271-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je CTL</span><span class="sxs-lookup"><span data-stu-id="7a271-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7a271-108">Operace, jejíž vstup má být obrácený.</span><span class="sxs-lookup"><span data-stu-id="7a271-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-ctl"></a><span data-ttu-id="7a271-109">Výstup: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je CTL</span><span class="sxs-lookup"><span data-stu-id="7a271-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7a271-110">Nová operace, která přijme svůj vstup jako registr Little endian.</span><span class="sxs-lookup"><span data-stu-id="7a271-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a271-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="7a271-111">See Also</span></span>

- [<span data-ttu-id="7a271-112">Microsoft. prostředníky. aritmetické. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="7a271-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="7a271-113">Microsoft. prostředníky. aritmetické. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="7a271-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="7a271-114">Microsoft. prostředníky. aritmetické. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="7a271-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="7a271-115">Microsoft. prostředníky. aritmetické. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="7a271-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)