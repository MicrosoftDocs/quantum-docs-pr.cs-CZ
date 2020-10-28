---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operace násobení
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706369"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="05011-102">Operace násobení</span><span class="sxs-lookup"><span data-stu-id="05011-102">MultiplyI operation</span></span>

<span data-ttu-id="05011-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="05011-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="05011-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05011-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05011-105">Vynásobit celé číslo `xs` `ys` a uložit výsledek do `result` , který musí být zpočátku nula.</span><span class="sxs-lookup"><span data-stu-id="05011-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="05011-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="05011-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="05011-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="05011-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="05011-108">$n $-bit multiplicand (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="05011-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="05011-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="05011-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="05011-110">$n $-bit násobitele (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="05011-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="05011-111">výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="05011-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="05011-112">$2N $-bit výsledek (LittleEndian), musí být ve stavu $ \ket {0} $ zpočátku.</span><span class="sxs-lookup"><span data-stu-id="05011-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05011-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05011-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="05011-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="05011-114">Remarks</span></span>

<span data-ttu-id="05011-115">K implementaci násobení slouží standardní přístup Shift-and-Add.</span><span class="sxs-lookup"><span data-stu-id="05011-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="05011-116">Řízená verze se vylepšila tak, že se $x _i $ do ancilla qubit v podmínce qubits ovládacího prvku a pak se řízení přidalo na ancilla qubit.</span><span class="sxs-lookup"><span data-stu-id="05011-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>