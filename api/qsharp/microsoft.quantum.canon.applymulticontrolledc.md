---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: Operace ApplyMultiControlledC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: bf6b78cd18a827a9a4fd9d61dfd4d240de3503e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844872"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="0f28e-102">Operace ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="0f28e-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="0f28e-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f28e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f28e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f28e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f28e-105">Aplikuje vynásobení kontrolované verze samostatně kontrolované operace.</span><span class="sxs-lookup"><span data-stu-id="0f28e-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="0f28e-106">Modifikátor `C` označuje, že operace s jedním qubit je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="0f28e-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="0f28e-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="0f28e-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="0f28e-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f28e-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0f28e-109">Operace řízená na jednom qubit.</span><span class="sxs-lookup"><span data-stu-id="0f28e-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="0f28e-110">První qubit v argumentu operace se považuje za ovládací prvek a zbytek se předpokládá jako cílový qubits.</span><span class="sxs-lookup"><span data-stu-id="0f28e-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="0f28e-111">`ApplyMultiControlled` vždy volá `singlyControlledOp` s argumentem délky alespoň 1.</span><span class="sxs-lookup"><span data-stu-id="0f28e-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="0f28e-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="0f28e-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="0f28e-113">Nekontrolovaná brána, která se má použít pro konstrukci.</span><span class="sxs-lookup"><span data-stu-id="0f28e-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="0f28e-114">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0f28e-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0f28e-115">Qubits, na kterém má `singlyControlledOp` být kontrolována.</span><span class="sxs-lookup"><span data-stu-id="0f28e-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="0f28e-116">Délka `controls` musí být aspoň 1.</span><span class="sxs-lookup"><span data-stu-id="0f28e-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="0f28e-117">cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0f28e-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0f28e-118">Cílová qubits, na které `singlyControlledOp` působí.</span><span class="sxs-lookup"><span data-stu-id="0f28e-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f28e-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f28e-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0f28e-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0f28e-120">Remarks</span></span>

<span data-ttu-id="0f28e-121">Tato operace používá pouze čistě ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="0f28e-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="0f28e-122">Diagram vysvětlení a okruhu viz obrázek 4,10, část 4,3 v Nielsen & Čuangština</span><span class="sxs-lookup"><span data-stu-id="0f28e-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="0f28e-123">Reference</span><span class="sxs-lookup"><span data-stu-id="0f28e-123">References</span></span>

- [<span data-ttu-id="0f28e-124">*Michal a. Nielsen, Petr L. Čuangština*, výpočet doby a informace o tom,</span><span class="sxs-lookup"><span data-stu-id="0f28e-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="0f28e-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="0f28e-125">See Also</span></span>

- [<span data-ttu-id="0f28e-126">Microsoft. proApplyMultiControlledCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="0f28e-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)