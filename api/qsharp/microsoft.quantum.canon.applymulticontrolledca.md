---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Operace ApplyMultiControlledCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: a6549084b1c2fda885823f451d17f9c2ebbb4600
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841681"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="b36c5-102">Operace ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="b36c5-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="b36c5-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b36c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b36c5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b36c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b36c5-105">Aplikuje vynásobení kontrolované verze samostatně kontrolované operace.</span><span class="sxs-lookup"><span data-stu-id="b36c5-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="b36c5-106">Modifikátor `CA` označuje, že operace s jedním qubit je ovladatelné a přiléhající.</span><span class="sxs-lookup"><span data-stu-id="b36c5-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b36c5-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="b36c5-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit--is-adj"></a><span data-ttu-id="b36c5-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="b36c5-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b36c5-109">Operace řízená na jednom qubit.</span><span class="sxs-lookup"><span data-stu-id="b36c5-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="b36c5-110">První qubit v argumentu operace předpokládá, že se jedná o ovládací prvek a že zbytek se považuje za cílový qubits.</span><span class="sxs-lookup"><span data-stu-id="b36c5-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="b36c5-111">`ApplyMultiControlled` vždy volá `singlyControlledOp` s argumentem délky alespoň 1.</span><span class="sxs-lookup"><span data-stu-id="b36c5-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="b36c5-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="b36c5-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="b36c5-113">Nekontrolovaná brána, která se má použít pro konstrukci.</span><span class="sxs-lookup"><span data-stu-id="b36c5-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="b36c5-114">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b36c5-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b36c5-115">Qubits, na kterém má `singlyControlledOp` být kontrolována.</span><span class="sxs-lookup"><span data-stu-id="b36c5-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="b36c5-116">Délka `controls` musí být aspoň 1.</span><span class="sxs-lookup"><span data-stu-id="b36c5-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="b36c5-117">cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b36c5-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b36c5-118">Cílová qubits, na které `singlyControlledOp` působí.</span><span class="sxs-lookup"><span data-stu-id="b36c5-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b36c5-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b36c5-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b36c5-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b36c5-120">Remarks</span></span>

<span data-ttu-id="b36c5-121">Tato operace používá pouze čistě ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="b36c5-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="b36c5-122">Diagram vysvětlení a okruhu viz obrázek 4,10, část 4,3 v Nielsen & Čuangština</span><span class="sxs-lookup"><span data-stu-id="b36c5-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="b36c5-123">Reference</span><span class="sxs-lookup"><span data-stu-id="b36c5-123">References</span></span>

- [<span data-ttu-id="b36c5-124">*Michal a. Nielsen, Petr L. Čuangština*, výpočet doby a informace o tom,</span><span class="sxs-lookup"><span data-stu-id="b36c5-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="b36c5-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="b36c5-125">See Also</span></span>

- [<span data-ttu-id="b36c5-126">Microsoft. proApplyMultiControlledC. Canon.</span><span class="sxs-lookup"><span data-stu-id="b36c5-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)