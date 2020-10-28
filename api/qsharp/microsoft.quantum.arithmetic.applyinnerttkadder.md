---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: Operace ApplyInnerTTKAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 23c1f6dcdf3894cf1b416efd922c9eed01ac8f85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707633"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="999a6-102">Operace ApplyInnerTTKAdder</span><span class="sxs-lookup"><span data-stu-id="999a6-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="999a6-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="999a6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="999a6-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="999a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="999a6-105">Implementuje funkci Inner sčítání pro operaci RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="999a6-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="999a6-106">Toto je vnitřní operace, která je sdružená s vnější operací pro vytvoření úplného přidávání.</span><span class="sxs-lookup"><span data-stu-id="999a6-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="999a6-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="999a6-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="999a6-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="999a6-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="999a6-109">LittleEndian qubit registruje kódování prvního celého čísla summand vstupu do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="999a6-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="999a6-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="999a6-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="999a6-111">LittleEndian qubit registruje kódování druhé celočíselné summand vstupu do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="999a6-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="999a6-112">přenést: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="999a6-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="999a6-113">Přenese qubit, je XORed s nejvýznamnějším bitem součtu.</span><span class="sxs-lookup"><span data-stu-id="999a6-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="999a6-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="999a6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="999a6-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="999a6-115">Remarks</span></span>

<span data-ttu-id="999a6-116">Určená řízená operace využívá symetrii a vzájemné rušení operací pro zlepšení výchozí implementace, která přidává ovládací prvek ke každé operaci.</span><span class="sxs-lookup"><span data-stu-id="999a6-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="999a6-117">Odkazy</span><span class="sxs-lookup"><span data-stu-id="999a6-117">References</span></span>

- <span data-ttu-id="999a6-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "dopředné a nevázané ventilátory, informace o všech procesorech a výpočet, obj. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="999a6-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530