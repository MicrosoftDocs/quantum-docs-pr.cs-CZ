---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840806"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="c4d53-102">ControlledOnBitString – funkce</span><span class="sxs-lookup"><span data-stu-id="c4d53-102">ControlledOnBitString function</span></span>

<span data-ttu-id="c4d53-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4d53-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4d53-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4d53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4d53-105">Vrátí jednotnou operaci, která použije Oracle v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadané bitové masce.</span><span class="sxs-lookup"><span data-stu-id="c4d53-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="c4d53-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c4d53-106">Description</span></span>

<span data-ttu-id="c4d53-107">Výstupem této funkce je operace, kterou může představovat jednotná transformace $U $ taková, že \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{Otherwise} \end{Cases}, \end{align}, kde $V $ je jednotná transformace, která představuje akci `oracle` operace.</span><span class="sxs-lookup"><span data-stu-id="c4d53-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="c4d53-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="c4d53-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="c4d53-109">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="c4d53-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="c4d53-110">Bitový řetězec, na kterém se má řídit daná Jednotková operace.</span><span class="sxs-lookup"><span data-stu-id="c4d53-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="c4d53-111">Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c4d53-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c4d53-112">Jednotná operace, která se má použít v cílovém registru.</span><span class="sxs-lookup"><span data-stu-id="c4d53-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="c4d53-113">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c4d53-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c4d53-114">Jednotná operace, která platí `oracle` v cílovém registru, pokud stav registru ovládacího prvku odpovídá bitové masce `bits` .</span><span class="sxs-lookup"><span data-stu-id="c4d53-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4d53-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c4d53-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4d53-116">'S</span><span class="sxs-lookup"><span data-stu-id="c4d53-116">'T</span></span>



## <a name="example"></a><span data-ttu-id="c4d53-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="c4d53-117">Example</span></span>

<span data-ttu-id="c4d53-118">Následující fragmenty kódu jsou ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="c4d53-118">The following code snippets are equivalent:</span></span>

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

<span data-ttu-id="c4d53-119">a</span><span class="sxs-lookup"><span data-stu-id="c4d53-119">and</span></span>

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

<span data-ttu-id="c4d53-120">Následující kód připraví stav $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $:</span><span class="sxs-lookup"><span data-stu-id="c4d53-120">The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:</span></span>

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a><span data-ttu-id="c4d53-121">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c4d53-121">Remarks</span></span>

<span data-ttu-id="c4d53-122">Vzor zadaný pomocí `bits` může být kratší než `controlRegister` , v takovém případě je další qubits ovládacího prvku ignorováno (to znamená, že není kontrolováno na $ \ket {0} $ ani $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="c4d53-122">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="c4d53-123">Pokud `bits` je delší než `controlRegister` , je vyvolána chyba.</span><span class="sxs-lookup"><span data-stu-id="c4d53-123">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="c4d53-124">V případě logického pole `bits` a jednotkové operace `oracle` je výstup této funkce operace, která provede následující kroky:</span><span class="sxs-lookup"><span data-stu-id="c4d53-124">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="c4d53-125">použijte `X` operaci na každý qubit registru ovládacího prvku, který odpovídá `false` elementu `bits` .</span><span class="sxs-lookup"><span data-stu-id="c4d53-125">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="c4d53-126">platí `Controlled oracle` pro Registry ovládacího prvku a cíle;</span><span class="sxs-lookup"><span data-stu-id="c4d53-126">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="c4d53-127">použijte `X` operaci na každý qubit registru ovládacího prvku, který odpovídá `false` elementu `bits` znovu a vrátí registraci ovládacího prvku do původního stavu.</span><span class="sxs-lookup"><span data-stu-id="c4d53-127">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="c4d53-128">Výstupem `Controlled` funktor je zvláštní případ, `ControlledOnBitString` kde `bits` je rovno `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="c4d53-128">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>