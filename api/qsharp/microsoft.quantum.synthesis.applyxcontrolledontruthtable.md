---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Operace ApplyXControlledOnTruthTable
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709184"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="2b494-102">Operace ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="2b494-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="2b494-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="2b494-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="2b494-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b494-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b494-105">Aplikuje @"microsoft.quantum.intrinsic.x" operaci na `target` , pokud je logická funkce `func` vyhodnocena jako true pro klasické přiřazení v `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="2b494-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="2b494-106">Popis</span><span class="sxs-lookup"><span data-stu-id="2b494-106">Description</span></span>

<span data-ttu-id="2b494-107">Operace implementuje jednotkovou operaci \begin{align} U\ket {x} \ KET {y} = \ket{x}\ket{y \oplus f (x)} \end{align}, kde $x $ a $y $ reprezentovat `controlRegister` a `target` v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="2b494-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="2b494-108">Funkce Boolean $f $ je reprezentovaná jako tabulka pravdy v podobě velkých celých čísel.</span><span class="sxs-lookup"><span data-stu-id="2b494-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="2b494-109">Například funkce většina na třech vstupech je reprezentovaná BITSTRING `11101000` , kde nejvýznamnější bit `1` odpovídá vstupnímu přiřazení `(1, 1, 1)` , a nejméně významný bit `0` odpovídá vstupnímu přiřazení `(0, 0, 0)` .</span><span class="sxs-lookup"><span data-stu-id="2b494-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="2b494-110">Může být reprezentována velkým celým číslem `0xE8L` v šestnáctkovém zápisu nebo jako `232L` Desítkový zápis.</span><span class="sxs-lookup"><span data-stu-id="2b494-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="2b494-111">`L`Přípona označuje, že konstanta je typu `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="2b494-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="2b494-112">Další podrobnosti o této prezentaci najdete také v tabulce [pravdy Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span><span class="sxs-lookup"><span data-stu-id="2b494-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="2b494-113">Implementace využívá @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" brány a.</span><span class="sxs-lookup"><span data-stu-id="2b494-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="2b494-114">Vstup</span><span class="sxs-lookup"><span data-stu-id="2b494-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="2b494-115">Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2b494-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2b494-116">Logická tabulka pravdy reprezentovaná jako velké celé číslo</span><span class="sxs-lookup"><span data-stu-id="2b494-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="2b494-117">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2b494-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2b494-118">Registrační qubits ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="2b494-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2b494-119">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2b494-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2b494-120">Cílový qubit</span><span class="sxs-lookup"><span data-stu-id="2b494-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b494-121">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b494-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="2b494-122">Odkazy</span><span class="sxs-lookup"><span data-stu-id="2b494-122">References</span></span>

- [<span data-ttu-id="2b494-123">*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv: quant-pH/0303063</span><span class="sxs-lookup"><span data-stu-id="2b494-123">*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="2b494-124">*Mathias Soeken* , *Martin Roetteler* , arXiv: 2005.12310</span><span class="sxs-lookup"><span data-stu-id="2b494-124">*Mathias Soeken* , *Martin Roetteler* , arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="2b494-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="2b494-125">See Also</span></span>

- [<span data-ttu-id="2b494-126">Microsoft. proshrnutí. ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="2b494-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)