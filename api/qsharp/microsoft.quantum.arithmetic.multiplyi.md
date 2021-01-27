---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operace násobení
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 8615d0d5100c26f86264ceaecadb7783563216a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843031"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="faad0-102">Operace násobení</span><span class="sxs-lookup"><span data-stu-id="faad0-102">MultiplyI operation</span></span>

<span data-ttu-id="faad0-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="faad0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="faad0-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="faad0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="faad0-105">Vynásobit celé číslo `xs` `ys` a uložit výsledek do `result` , který musí být zpočátku nula.</span><span class="sxs-lookup"><span data-stu-id="faad0-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="faad0-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="faad0-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="faad0-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="faad0-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="faad0-108">$n $-bit multiplicand (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="faad0-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="faad0-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="faad0-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="faad0-110">$n $-bit násobitele (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="faad0-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="faad0-111">výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="faad0-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="faad0-112">$2N $-bit výsledek (LittleEndian), musí být ve stavu $ \ket {0} $ zpočátku.</span><span class="sxs-lookup"><span data-stu-id="faad0-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="faad0-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="faad0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="faad0-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="faad0-114">Remarks</span></span>

<span data-ttu-id="faad0-115">K implementaci násobení slouží standardní přístup Shift-and-Add.</span><span class="sxs-lookup"><span data-stu-id="faad0-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="faad0-116">Řízená verze se vylepšila tak, že se $x _i $ do ancilla qubit v podmínce qubits ovládacího prvku a pak se řízení přidalo na ancilla qubit.</span><span class="sxs-lookup"><span data-stu-id="faad0-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>