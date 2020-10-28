---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: Operace ApplyInnerTTKAdderWithoutCarry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 3335c63b8509090deed1172419158da0d5e80409
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707625"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="06f23-102">Operace ApplyInnerTTKAdderWithoutCarry</span><span class="sxs-lookup"><span data-stu-id="06f23-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="06f23-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="06f23-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="06f23-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06f23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06f23-105">Implementuje funkci Inner sčítání pro operaci RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="06f23-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="06f23-106">Toto je vnitřní operace, která je sdružená s vnější operací pro vytvoření úplného přidávání.</span><span class="sxs-lookup"><span data-stu-id="06f23-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="06f23-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="06f23-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="06f23-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="06f23-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="06f23-109">LittleEndian qubit registruje kódování prvního celého čísla summand vstupu do RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="06f23-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="06f23-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="06f23-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="06f23-111">LittleEndian qubit registruje kódování druhé celočíselné summand vstupu do RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="06f23-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="06f23-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06f23-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="06f23-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="06f23-113">Remarks</span></span>

<span data-ttu-id="06f23-114">Určená řízená operace využívá symetrii a vzájemné rušení operací pro zlepšení výchozí implementace, která přidává ovládací prvek ke každé operaci.</span><span class="sxs-lookup"><span data-stu-id="06f23-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="06f23-115">Odkazy</span><span class="sxs-lookup"><span data-stu-id="06f23-115">References</span></span>

- <span data-ttu-id="06f23-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "dopředné a nevázané ventilátory, informace o všech procesorech a výpočet, obj. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="06f23-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530