---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: Operace ApplyInnerTTKAdder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: c822933340d592061eb039af7c6e438212abc265
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843837"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="688c8-102">Operace ApplyInnerTTKAdder</span><span class="sxs-lookup"><span data-stu-id="688c8-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="688c8-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="688c8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="688c8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="688c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="688c8-105">Implementuje funkci Inner sčítání pro operaci RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="688c8-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="688c8-106">Toto je vnitřní operace, která je sdružená s vnější operací pro vytvoření úplného přidávání.</span><span class="sxs-lookup"><span data-stu-id="688c8-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="688c8-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="688c8-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="688c8-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="688c8-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="688c8-109">LittleEndian qubit registruje kódování prvního celého čísla summand vstupu do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="688c8-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="688c8-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="688c8-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="688c8-111">LittleEndian qubit registruje kódování druhé celočíselné summand vstupu do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="688c8-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="688c8-112">přenést: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="688c8-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="688c8-113">Přenese qubit, je XORed s nejvýznamnějším bitem součtu.</span><span class="sxs-lookup"><span data-stu-id="688c8-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="688c8-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="688c8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="688c8-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="688c8-115">Remarks</span></span>

<span data-ttu-id="688c8-116">Určená řízená operace využívá symetrii a vzájemné rušení operací pro zlepšení výchozí implementace, která přidává ovládací prvek ke každé operaci.</span><span class="sxs-lookup"><span data-stu-id="688c8-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="688c8-117">Reference</span><span class="sxs-lookup"><span data-stu-id="688c8-117">References</span></span>

- <span data-ttu-id="688c8-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "dopředné a nevázané ventilátory, informace o všech procesorech a výpočet, obj. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="688c8-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530