---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operace CopyMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843273"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="c5d4b-102">Operace CopyMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="c5d4b-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="c5d4b-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c5d4b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c5d4b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5d4b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5d4b-105">Zkopíruje nejvýznamnější bit qubit registru `from` reprezentujícího unsigned integer do qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="c5d4b-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="c5d4b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c5d4b-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="c5d4b-107">z: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5d4b-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c5d4b-108">Unsigned integer, ze kterých se kopíruje nejvyšší bit.</span><span class="sxs-lookup"><span data-stu-id="c5d4b-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="c5d4b-109">celé číslo je kódováno ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="c5d4b-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c5d4b-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c5d4b-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c5d4b-111">Qubit, do kterého se kopíruje nejvyšší bit.</span><span class="sxs-lookup"><span data-stu-id="c5d4b-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="c5d4b-112">Bitové kódování je v výpočetních intervalech.</span><span class="sxs-lookup"><span data-stu-id="c5d4b-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5d4b-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5d4b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c5d4b-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="c5d4b-114">See Also</span></span>

- [<span data-ttu-id="c5d4b-115">Microsoft. prostředníky. aritmetické. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="c5d4b-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)