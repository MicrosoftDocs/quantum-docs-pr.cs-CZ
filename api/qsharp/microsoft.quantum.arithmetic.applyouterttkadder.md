---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: Operace ApplyOuterTTKAdder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: aed15a4d1f3ca7121d6da665f5c08442fd495619
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190611"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="13dcf-102">Operace ApplyOuterTTKAdder</span><span class="sxs-lookup"><span data-stu-id="13dcf-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="13dcf-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="13dcf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="13dcf-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13dcf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13dcf-105">Implementuje vnější operaci pro RippleCarryAdderTTK k vytvoření úplného přidaných vnitřních operací.</span><span class="sxs-lookup"><span data-stu-id="13dcf-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="13dcf-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="13dcf-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="13dcf-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="13dcf-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="13dcf-108">LittleEndian qubit registruje kódování prvního celého čísla summand vstupu do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="13dcf-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="13dcf-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="13dcf-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="13dcf-110">LittleEndian qubit registruje kódování druhé celočíselné summand vstupu do RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="13dcf-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="13dcf-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13dcf-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="13dcf-112">Reference</span><span class="sxs-lookup"><span data-stu-id="13dcf-112">References</span></span>

- <span data-ttu-id="13dcf-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "dopředné a nevázané ventilátory, informace o všech procesorech a výpočet, obj. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="13dcf-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530