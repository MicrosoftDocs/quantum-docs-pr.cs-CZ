---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Operace ApplyXControlledOnTruthTableWithCleanTarget
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: a54544cd026f26784bb0c41cb12187a8885ed9db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855533"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="f3b5b-102">Operace ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="f3b5b-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="f3b5b-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f3b5b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f3b5b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3b5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3b5b-105">Aplikuje @"microsoft.quantum.intrinsic.x" operaci na `target` , pokud je logická funkce `func` vyhodnocena jako true pro klasické přiřazení v `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="f3b5b-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f3b5b-106">Popis</span><span class="sxs-lookup"><span data-stu-id="f3b5b-106">Description</span></span>

<span data-ttu-id="f3b5b-107">Tato operace implementuje zvláštní případ @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , ve kterém je známý cílový qubit ve stavu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="f3b5b-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="f3b5b-108">Implementace využívá @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" brány a.</span><span class="sxs-lookup"><span data-stu-id="f3b5b-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="f3b5b-109">Implementace sousedících operací se optimalizuje a používá nevýpočetní na základě měření.</span><span class="sxs-lookup"><span data-stu-id="f3b5b-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="f3b5b-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="f3b5b-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="f3b5b-111">Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f3b5b-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f3b5b-112">Logická tabulka pravdy reprezentovaná jako velké celé číslo</span><span class="sxs-lookup"><span data-stu-id="f3b5b-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="f3b5b-113">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f3b5b-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f3b5b-114">Registrační qubits ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="f3b5b-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f3b5b-115">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f3b5b-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f3b5b-116">Cílový qubit (musí být ve stavu $ \ket {0} $)</span><span class="sxs-lookup"><span data-stu-id="f3b5b-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3b5b-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3b5b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f3b5b-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="f3b5b-118">See Also</span></span>

- [<span data-ttu-id="f3b5b-119">Microsoft. proshrnutí. ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="f3b5b-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)