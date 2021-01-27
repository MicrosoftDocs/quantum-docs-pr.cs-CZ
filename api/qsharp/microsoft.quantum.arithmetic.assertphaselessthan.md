---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Operace AssertPhaseLessThan
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 7b7a4fea8973727da4dcab6f739c6db8da835a2f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843434"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="a029a-102">Operace AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="a029a-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="a029a-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a029a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a029a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a029a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a029a-105">Vyhodnotí, že `number` kódovaný v PhaseLittleEndian je menší než `value` .</span><span class="sxs-lookup"><span data-stu-id="a029a-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a029a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a029a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="a029a-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a029a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a029a-108">`number` musí být menší než to.</span><span class="sxs-lookup"><span data-stu-id="a029a-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="a029a-109">číslo: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a029a-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="a029a-110">Celé číslo bez znaménka, které je porovnáno s `value` .</span><span class="sxs-lookup"><span data-stu-id="a029a-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a029a-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a029a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a029a-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a029a-112">Remarks</span></span>

<span data-ttu-id="a029a-113">Řízená verze této operace ignoruje ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="a029a-113">The controlled version of this operation ignores controls.</span></span>