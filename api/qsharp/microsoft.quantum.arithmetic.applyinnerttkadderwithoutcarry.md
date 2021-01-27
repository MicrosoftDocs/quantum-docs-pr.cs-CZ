---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: Operace ApplyInnerTTKAdderWithoutCarry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 0c1626c788215181b5ed45dc98bed928b5e4848a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843805"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="486d1-102">Operace ApplyInnerTTKAdderWithoutCarry</span><span class="sxs-lookup"><span data-stu-id="486d1-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="486d1-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="486d1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="486d1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="486d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="486d1-105">Implementuje funkci Inner sčítání pro operaci RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="486d1-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="486d1-106">Toto je vnitřní operace, která je sdružená s vnější operací pro vytvoření úplného přidávání.</span><span class="sxs-lookup"><span data-stu-id="486d1-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="486d1-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="486d1-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="486d1-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="486d1-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="486d1-109">LittleEndian qubit registruje kódování prvního celého čísla summand vstupu do RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="486d1-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="486d1-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="486d1-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="486d1-111">LittleEndian qubit registruje kódování druhé celočíselné summand vstupu do RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="486d1-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="486d1-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="486d1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="486d1-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="486d1-113">Remarks</span></span>

<span data-ttu-id="486d1-114">Určená řízená operace využívá symetrii a vzájemné rušení operací pro zlepšení výchozí implementace, která přidává ovládací prvek ke každé operaci.</span><span class="sxs-lookup"><span data-stu-id="486d1-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="486d1-115">Reference</span><span class="sxs-lookup"><span data-stu-id="486d1-115">References</span></span>

- <span data-ttu-id="486d1-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "dopředné a nevázané ventilátory, informace o všech procesorech a výpočet, obj. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="486d1-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530