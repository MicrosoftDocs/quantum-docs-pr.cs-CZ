---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: b8eff9d207752213ccdf42a9ad80fefb2da07216
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708614"
---
# <a name="blockencodingreflectionbylcu-function"></a><span data-ttu-id="b4d39-102">BlockEncodingReflectionByLCU – funkce</span><span class="sxs-lookup"><span data-stu-id="b4d39-102">BlockEncodingReflectionByLCU function</span></span>

<span data-ttu-id="b4d39-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b4d39-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b4d39-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4d39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4d39-105">Zakóduje operátor zájmu do `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="b4d39-105">Encodes an operator of interest into a `BlockEncodingReflection`.</span></span>

<span data-ttu-id="b4d39-106">Tato konstrukce vytvoří `BlockEncodingReflection` jednotkovou $U = P\cdot V\cdot P ^ \dagger $, který kóduje nějaký operátor $H = \ sum_ {j} | \ alpha_j | U_j $ z zájmu je lineární kombinací unitaries.</span><span class="sxs-lookup"><span data-stu-id="b4d39-106">This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="b4d39-107">$P $ je typicky Příprava stavu, takže $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ a $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="b4d39-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="b4d39-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="b4d39-108">Input</span></span>

### <a name="statepreparation--qubit--unit-adj--ctl"></a><span data-ttu-id="b4d39-109">statePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="b4d39-109">statePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b4d39-110">Jednotková $P $, která připraví určitý cílový stav.</span><span class="sxs-lookup"><span data-stu-id="b4d39-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="b4d39-111">selektor: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="b4d39-111">selector : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b4d39-112">Jednotková $V $, která kóduje komponentu unitaries $H $.</span><span class="sxs-lookup"><span data-stu-id="b4d39-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="b4d39-113">Výstup: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="b4d39-113">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="b4d39-114">Jednotná $U $ pracuje společně na registrech `a` a `s` zablokuje $H $ a splňuje $U ^ {-1} = U $.</span><span class="sxs-lookup"><span data-stu-id="b4d39-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^{-1} = U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4d39-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b4d39-115">Remarks</span></span>

<span data-ttu-id="b4d39-116">Tato `BlockEncoding` implementace poskytuje vlastnosti `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="b4d39-116">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4d39-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="b4d39-117">See Also</span></span>

- [<span data-ttu-id="b4d39-118">Microsoft. v. simulace. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="b4d39-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="b4d39-119">Microsoft. v. simulace. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="b4d39-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)