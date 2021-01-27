---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 392b97171bcfb9d35a38189fc9c27e61cf9cf7d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846459"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="a3022-102">ReversedOpBEA – funkce</span><span class="sxs-lookup"><span data-stu-id="a3022-102">ReversedOpBEA function</span></span>

<span data-ttu-id="a3022-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a3022-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a3022-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3022-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3022-105">Vzhledem k operaci, která trvá vstupu big-endian, vrátí novou operaci, která bude mít vstup ze Little endian.</span><span class="sxs-lookup"><span data-stu-id="a3022-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="a3022-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a3022-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="a3022-107">op: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je ADJ.</span><span class="sxs-lookup"><span data-stu-id="a3022-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a3022-108">Operace, jejíž vstup má být obrácený.</span><span class="sxs-lookup"><span data-stu-id="a3022-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj"></a><span data-ttu-id="a3022-109">Výstup: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ.</span><span class="sxs-lookup"><span data-stu-id="a3022-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a3022-110">Nová operace, která přijme svůj vstup jako registr Little endian.</span><span class="sxs-lookup"><span data-stu-id="a3022-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3022-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="a3022-111">See Also</span></span>

- [<span data-ttu-id="a3022-112">Microsoft. prostředníky. aritmetické. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="a3022-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="a3022-113">Microsoft. prostředníky. aritmetické. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="a3022-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="a3022-114">Microsoft. prostředníky. aritmetické. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="a3022-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="a3022-115">Microsoft. prostředníky. aritmetické. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="a3022-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)