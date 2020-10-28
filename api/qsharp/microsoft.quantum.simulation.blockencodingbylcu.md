---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709021"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="0d642-102">BlockEncodingByLCU – funkce</span><span class="sxs-lookup"><span data-stu-id="0d642-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="0d642-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0d642-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0d642-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d642-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d642-105">Zakóduje operátor zájmu do `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="0d642-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="0d642-106">Tato konstrukce vytvoří `BlockEncoding` jednotkovou $U = P\cdot V\cdot P ^ \dagger $, který kóduje nějaký operátor $H = \ sum_ {j} | \ alpha_j | U_j $ z zájmu je lineární kombinací unitaries.</span><span class="sxs-lookup"><span data-stu-id="0d642-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="0d642-107">$P $ je obvykle státní příprava, takže $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ a $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="0d642-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="0d642-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="0d642-108">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="0d642-109">statePreparation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="0d642-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0d642-110">Jednotková $P $, která připraví určitý cílový stav.</span><span class="sxs-lookup"><span data-stu-id="0d642-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="0d642-111">selektor: (t, ') => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="0d642-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0d642-112">Jednotková $V $, která kóduje komponentu unitaries $H $.</span><span class="sxs-lookup"><span data-stu-id="0d642-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit-adj--ctl"></a><span data-ttu-id="0d642-113">Výstup: (t, 'S) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="0d642-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0d642-114">Jednotná $U $ pracuje společně na registrech `a` a `s` zablokuje $H $ a splňuje $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="0d642-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0d642-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0d642-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d642-116">'S</span><span class="sxs-lookup"><span data-stu-id="0d642-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="0d642-117">Jeho</span><span class="sxs-lookup"><span data-stu-id="0d642-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="0d642-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0d642-118">Remarks</span></span>

<span data-ttu-id="0d642-119">Tato `BlockEncoding` implementace poskytuje vlastnosti `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="0d642-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d642-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="0d642-120">See Also</span></span>

- [<span data-ttu-id="0d642-121">Microsoft. v. simulace. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="0d642-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="0d642-122">Microsoft. v. simulace. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="0d642-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)