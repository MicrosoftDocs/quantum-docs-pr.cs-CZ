---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: Operace ApplyOuterTTKAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: 3d6d7c3446075130e5a8ee93abbd27e617d50b3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707569"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="c668c-102">Operace ApplyOuterTTKAdder</span><span class="sxs-lookup"><span data-stu-id="c668c-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="c668c-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c668c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c668c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c668c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c668c-105">Implementuje vnější operaci pro RippleCarryAdderTTK k vytvoření úplného přidaných vnitřních operací.</span><span class="sxs-lookup"><span data-stu-id="c668c-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="c668c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c668c-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c668c-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c668c-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c668c-108">LittleEndian qubit registruje kódování prvního celého čísla summand vstupu do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="c668c-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c668c-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c668c-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c668c-110">LittleEndian qubit registruje kódování druhé celočíselné summand vstupu do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="c668c-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c668c-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c668c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="c668c-112">Odkazy</span><span class="sxs-lookup"><span data-stu-id="c668c-112">References</span></span>

- <span data-ttu-id="c668c-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "dopředné a nevázané ventilátory, informace o všech procesorech a výpočet, obj. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="c668c-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530