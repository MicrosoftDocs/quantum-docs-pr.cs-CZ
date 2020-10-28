---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Operace ApplyXControlledOnTruthTableWithCleanTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709178"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="27688-102">Operace ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="27688-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="27688-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="27688-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="27688-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27688-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27688-105">Aplikuje @"microsoft.quantum.intrinsic.x" operaci na `target` , pokud je logická funkce `func` vyhodnocena jako true pro klasické přiřazení v `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="27688-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="27688-106">Popis</span><span class="sxs-lookup"><span data-stu-id="27688-106">Description</span></span>

<span data-ttu-id="27688-107">Tato operace implementuje zvláštní případ @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , ve kterém je známý cílový qubit ve stavu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="27688-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="27688-108">Implementace využívá @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" brány a.</span><span class="sxs-lookup"><span data-stu-id="27688-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="27688-109">Implementace sousedících operací se optimalizuje a používá nevýpočetní na základě měření.</span><span class="sxs-lookup"><span data-stu-id="27688-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="27688-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="27688-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="27688-111">Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="27688-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="27688-112">Logická tabulka pravdy reprezentovaná jako velké celé číslo</span><span class="sxs-lookup"><span data-stu-id="27688-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="27688-113">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="27688-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="27688-114">Registrační qubits ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="27688-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="27688-115">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27688-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27688-116">Cílový qubit (musí být ve stavu $ \ket {0} $)</span><span class="sxs-lookup"><span data-stu-id="27688-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="27688-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27688-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="27688-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="27688-118">See Also</span></span>

- [<span data-ttu-id="27688-119">Microsoft. proshrnutí. ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="27688-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)