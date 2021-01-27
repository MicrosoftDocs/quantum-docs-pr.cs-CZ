---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d02817e5372b841f3ab633cafa22af603c5310c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846399"
---
# <a name="reversedople-function"></a><span data-ttu-id="0d36e-102">ReversedOpLE – funkce</span><span class="sxs-lookup"><span data-stu-id="0d36e-102">ReversedOpLE function</span></span>

<span data-ttu-id="0d36e-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0d36e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0d36e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d36e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d36e-105">Vzhledem k operaci, která trvá vstupu Little-endian, vrátí novou operaci, která bude mít vstup big-endian.</span><span class="sxs-lookup"><span data-stu-id="0d36e-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="0d36e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0d36e-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="0d36e-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="0d36e-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0d36e-108">Operace, jejíž vstup má být obrácený.</span><span class="sxs-lookup"><span data-stu-id="0d36e-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="0d36e-109">Výstup: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="0d36e-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0d36e-110">Nová operace, která přijme svůj vstup jako registr big-endian.</span><span class="sxs-lookup"><span data-stu-id="0d36e-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d36e-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="0d36e-111">See Also</span></span>

- [<span data-ttu-id="0d36e-112">Microsoft. prostředníky. aritmetické. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="0d36e-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="0d36e-113">Microsoft. prostředníky. aritmetické. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="0d36e-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="0d36e-114">Microsoft. prostředníky. aritmetické. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="0d36e-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="0d36e-115">Microsoft. prostředníky. aritmetické. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="0d36e-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)