---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operace AssertMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707449"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="054bd-102">Operace AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="054bd-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="054bd-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="054bd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="054bd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="054bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="054bd-105">Vyhodnotí, že nejvýznamnější qubit registru qubit, který představuje unsigned integer, je v určitém stavu.</span><span class="sxs-lookup"><span data-stu-id="054bd-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="054bd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="054bd-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="054bd-107">hodnota: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="054bd-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="054bd-108">Hodnota nejvyššího bitu, který je využíván jako kontrolní výraz.</span><span class="sxs-lookup"><span data-stu-id="054bd-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="054bd-109">číslo: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="054bd-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="054bd-110">Celé číslo bez znaménka, z něhož je zaškrtnuto nejvyšší bit.</span><span class="sxs-lookup"><span data-stu-id="054bd-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="054bd-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="054bd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="054bd-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="054bd-112">Remarks</span></span>

<span data-ttu-id="054bd-113">Řízená verze této operace ignoruje ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="054bd-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="054bd-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="054bd-114">See Also</span></span>

- [<span data-ttu-id="054bd-115">Microsoft. v. vnitřní. Assert</span><span class="sxs-lookup"><span data-stu-id="054bd-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)