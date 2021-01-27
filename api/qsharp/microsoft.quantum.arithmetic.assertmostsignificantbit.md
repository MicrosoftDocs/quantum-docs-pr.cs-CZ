---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operace AssertMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843427"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="b167b-102">Operace AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="b167b-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="b167b-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b167b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b167b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b167b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b167b-105">Vyhodnotí, že nejvýznamnější qubit registru qubit, který představuje unsigned integer, je v určitém stavu.</span><span class="sxs-lookup"><span data-stu-id="b167b-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b167b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b167b-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="b167b-107">hodnota: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="b167b-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="b167b-108">Hodnota nejvyššího bitu, který je využíván jako kontrolní výraz.</span><span class="sxs-lookup"><span data-stu-id="b167b-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="b167b-109">číslo: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b167b-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b167b-110">Celé číslo bez znaménka, z něhož je zaškrtnuto nejvyšší bit.</span><span class="sxs-lookup"><span data-stu-id="b167b-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b167b-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b167b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b167b-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b167b-112">Remarks</span></span>

<span data-ttu-id="b167b-113">Řízená verze této operace ignoruje ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="b167b-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="b167b-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="b167b-114">See Also</span></span>

- [<span data-ttu-id="b167b-115">Microsoft. v. vnitřní. Assert</span><span class="sxs-lookup"><span data-stu-id="b167b-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)