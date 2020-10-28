---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operace CopyMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707337"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="d6261-102">Operace CopyMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="d6261-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="d6261-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d6261-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d6261-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6261-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6261-105">Zkopíruje nejvýznamnější bit qubit registru `from` reprezentujícího unsigned integer do qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="d6261-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d6261-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d6261-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="d6261-107">z: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d6261-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d6261-108">Unsigned integer, ze kterých se kopíruje nejvyšší bit.</span><span class="sxs-lookup"><span data-stu-id="d6261-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="d6261-109">celé číslo je kódováno ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="d6261-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d6261-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d6261-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d6261-111">Qubit, do kterého se kopíruje nejvyšší bit.</span><span class="sxs-lookup"><span data-stu-id="d6261-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="d6261-112">Bitové kódování je v výpočetních intervalech.</span><span class="sxs-lookup"><span data-stu-id="d6261-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6261-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6261-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d6261-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="d6261-114">See Also</span></span>

- [<span data-ttu-id="d6261-115">Microsoft. prostředníky. aritmetické. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="d6261-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)