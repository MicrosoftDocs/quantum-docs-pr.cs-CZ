---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Operace ApplyOuterCDKMAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707576"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="88530-102">Operace ApplyOuterCDKMAdder</span><span class="sxs-lookup"><span data-stu-id="88530-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="88530-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="88530-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="88530-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="88530-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="88530-105">Vratný, místní Ripple – operace, která se používá v operaci sčítání celého čísla RippleCarryAdderCDKM níže.</span><span class="sxs-lookup"><span data-stu-id="88530-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="88530-106">Vzhledem k dvěma registrům qubit `xs` a `ys` stejné délce operace použije Ripple sekvenci pro CNOT a CCNOT brány s qubits v `xs` a `ys` jako ovládací prvky a qubits v `xs` jako cíle.</span><span class="sxs-lookup"><span data-stu-id="88530-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="88530-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="88530-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="88530-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88530-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="88530-109">První qubit registr obsahující ovládací prvky a cíle.</span><span class="sxs-lookup"><span data-stu-id="88530-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="88530-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88530-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="88530-111">Druhý qubit registr přispívá k ovládacím prvkům.</span><span class="sxs-lookup"><span data-stu-id="88530-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="88530-112">ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="88530-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="88530-113">Do této operace byla předána ancilla qubit použitá v RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="88530-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88530-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88530-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="88530-115">Odkazy</span><span class="sxs-lookup"><span data-stu-id="88530-115">References</span></span>

- <span data-ttu-id="88530-116">Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton: "nové v rámci Ripple – přenést okruh", 2004.</span><span class="sxs-lookup"><span data-stu-id="88530-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1