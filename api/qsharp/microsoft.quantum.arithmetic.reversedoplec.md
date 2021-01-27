---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 2dc6a596970f909af9c329dbe7002c165854cfec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846385"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="f5111-102">ReversedOpLEC – funkce</span><span class="sxs-lookup"><span data-stu-id="f5111-102">ReversedOpLEC function</span></span>

<span data-ttu-id="f5111-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f5111-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f5111-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5111-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5111-105">Vzhledem k operaci, která trvá vstupu Little-endian, vrátí novou operaci, která bude mít vstup big-endian.</span><span class="sxs-lookup"><span data-stu-id="f5111-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="f5111-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f5111-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="f5111-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je CTL</span><span class="sxs-lookup"><span data-stu-id="f5111-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f5111-108">Operace, jejíž vstup má být obrácený.</span><span class="sxs-lookup"><span data-stu-id="f5111-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-ctl"></a><span data-ttu-id="f5111-109">Výstup: [](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je CTL</span><span class="sxs-lookup"><span data-stu-id="f5111-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f5111-110">Nová operace, která přijme svůj vstup jako registr big-endian.</span><span class="sxs-lookup"><span data-stu-id="f5111-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5111-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="f5111-111">See Also</span></span>

- [<span data-ttu-id="f5111-112">Microsoft. prostředníky. aritmetické. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="f5111-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="f5111-113">Microsoft. prostředníky. aritmetické. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="f5111-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="f5111-114">Microsoft. prostředníky. aritmetické. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="f5111-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="f5111-115">Microsoft. prostředníky. aritmetické. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="f5111-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)