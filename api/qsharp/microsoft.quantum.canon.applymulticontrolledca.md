---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Operace ApplyMultiControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705193"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="b0e6a-102">Operace ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="b0e6a-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="b0e6a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b0e6a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b0e6a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b0e6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b0e6a-105">Aplikuje vynásobení kontrolované verze samostatně kontrolované operace.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="b0e6a-106">Modifikátor `CA` označuje, že operace s jedním qubit je ovladatelné a přiléhající.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b0e6a-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="b0e6a-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit-adj"></a><span data-ttu-id="b0e6a-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="b0e6a-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="b0e6a-109">Operace řízená na jednom qubit.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="b0e6a-110">První qubit v argumentu operace předpokládá, že se jedná o ovládací prvek a že zbytek se považuje za cílový qubits.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="b0e6a-111">`ApplyMultiControlled` vždy volá `singlyControlledOp` s argumentem délky alespoň 1.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="b0e6a-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="b0e6a-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="b0e6a-113">Nekontrolovaná brána, která se má použít pro konstrukci.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="b0e6a-114">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b0e6a-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b0e6a-115">Qubits, na kterém má `singlyControlledOp` být kontrolována.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="b0e6a-116">Délka `controls` musí být aspoň 1.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="b0e6a-117">cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b0e6a-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b0e6a-118">Cílová qubits, na které `singlyControlledOp` působí.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0e6a-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0e6a-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b0e6a-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b0e6a-120">Remarks</span></span>

<span data-ttu-id="b0e6a-121">Tato operace používá pouze čistě ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="b0e6a-122">Diagram vysvětlení a okruhu viz obrázek 4,10, část 4,3 v Nielsen & Čuangština</span><span class="sxs-lookup"><span data-stu-id="b0e6a-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="b0e6a-123">Odkazy</span><span class="sxs-lookup"><span data-stu-id="b0e6a-123">References</span></span>

- [<span data-ttu-id="b0e6a-124">*Michal a. Nielsen, Petr L. Čuangština* , výpočet doby a informace o tom,</span><span class="sxs-lookup"><span data-stu-id="b0e6a-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="b0e6a-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="b0e6a-125">See Also</span></span>

- [<span data-ttu-id="b0e6a-126">Microsoft. proApplyMultiControlledC. Canon.</span><span class="sxs-lookup"><span data-stu-id="b0e6a-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)