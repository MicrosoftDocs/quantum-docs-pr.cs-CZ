---
uid: Microsoft.Quantum.Canon.AndLadder
title: Operace AndLadder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845226"
---
# <a name="andladder-operation"></a><span data-ttu-id="a0485-102">Operace AndLadder</span><span class="sxs-lookup"><span data-stu-id="a0485-102">AndLadder operation</span></span>

<span data-ttu-id="a0485-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a0485-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a0485-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0485-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a0485-105">Provede řízený "a žebřík" v registru cílového qubits.</span><span class="sxs-lookup"><span data-stu-id="a0485-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="a0485-106">Popis</span><span class="sxs-lookup"><span data-stu-id="a0485-106">Description</span></span>

<span data-ttu-id="a0485-107">Tato operace používá transformaci popsanou následujícím mapováním výpočetního základu, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ WHERE $ \ket{x \_ 1, \dots, x \_ n} $ odkazuje na výpočetní stavy na bázi `controls` a kde $ \ket{y \_ 1, \dots, y \_ {n-1}} $ odkazuje na výpočetní stavy pro `targets` .</span><span class="sxs-lookup"><span data-stu-id="a0485-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="a0485-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="a0485-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="a0485-109">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="a0485-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="a0485-110">Brána CCNOT, která se má použít pro konstrukci</span><span class="sxs-lookup"><span data-stu-id="a0485-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="a0485-111">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a0485-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a0485-112">Registr qubits, který se má použít jako ovládací prvky pro žebřík a.</span><span class="sxs-lookup"><span data-stu-id="a0485-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="a0485-113">Tato operace opouští výpočetní základní stav `controls` invariantní.</span><span class="sxs-lookup"><span data-stu-id="a0485-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="a0485-114">Délka `controls` musí být alespoň 2 a musí být rovna jedné hodnotě plus délka `targets` .</span><span class="sxs-lookup"><span data-stu-id="a0485-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="a0485-115">cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a0485-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a0485-116">Délka `targets` musí být alespoň 1 a rovná se délce `controls` minus jedna.</span><span class="sxs-lookup"><span data-stu-id="a0485-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a0485-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a0485-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a0485-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a0485-118">Remarks</span></span>

- <span data-ttu-id="a0485-119">Používá se jako součást <xref:microsoft.quantum.canon.applymulticontrolledc> a <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="a0485-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="a0485-120">Diagram vysvětlení a okruhu viz obrázek 4,10, část 4,3 v Nielsen & Čuangština.</span><span class="sxs-lookup"><span data-stu-id="a0485-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="a0485-121">Reference</span><span class="sxs-lookup"><span data-stu-id="a0485-121">References</span></span>

- [<span data-ttu-id="a0485-122">*Michal a. Nielsen, Petr L. Čuangština*, výpočet doby a informace o tom,</span><span class="sxs-lookup"><span data-stu-id="a0485-122"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)