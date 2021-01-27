---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 878b0fae8a803b3136d1537309c945c052e1052c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846488"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="061e3-102">ReversedOpBE – funkce</span><span class="sxs-lookup"><span data-stu-id="061e3-102">ReversedOpBE function</span></span>

<span data-ttu-id="061e3-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="061e3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="061e3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="061e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="061e3-105">Vzhledem k operaci, která trvá vstupu big-endian, vrátí novou operaci, která bude mít vstup ze Little endian.</span><span class="sxs-lookup"><span data-stu-id="061e3-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="061e3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="061e3-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="061e3-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="061e3-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="061e3-108">Operace, jejíž vstup má být obrácený.</span><span class="sxs-lookup"><span data-stu-id="061e3-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="061e3-109">Výstup: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="061e3-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="061e3-110">Nová operace, která přijme svůj vstup jako registr Little endian.</span><span class="sxs-lookup"><span data-stu-id="061e3-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="061e3-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="061e3-111">See Also</span></span>

- [<span data-ttu-id="061e3-112">Microsoft. prostředníky. aritmetické. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="061e3-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="061e3-113">Microsoft. prostředníky. aritmetické. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="061e3-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="061e3-114">Microsoft. prostředníky. aritmetické. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="061e3-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="061e3-115">Microsoft. prostředníky. aritmetické. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="061e3-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)