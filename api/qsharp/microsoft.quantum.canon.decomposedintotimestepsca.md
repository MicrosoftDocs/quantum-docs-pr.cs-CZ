---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704265"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="6aedb-102">DecomposedIntoTimeStepsCA – funkce</span><span class="sxs-lookup"><span data-stu-id="6aedb-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="6aedb-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6aedb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6aedb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6aedb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6aedb-105">Vrátí operaci implementující integrátoru Trotter – Suzuki pro danou operaci.</span><span class="sxs-lookup"><span data-stu-id="6aedb-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="6aedb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6aedb-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="6aedb-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6aedb-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6aedb-108">Počet operací rozloženého na časové kroky.</span><span class="sxs-lookup"><span data-stu-id="6aedb-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="6aedb-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="6aedb-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6aedb-110">Operace, která přijímá vstup indexu (typ `Int` ) a vstupní čas (typ `Double` ) pro rozklad.</span><span class="sxs-lookup"><span data-stu-id="6aedb-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="6aedb-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6aedb-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6aedb-112">Vybere pořadí, ve kterém se má použít integrátor Trotter-Suzuki.</span><span class="sxs-lookup"><span data-stu-id="6aedb-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="6aedb-113">Objednávka 1 a dokonce i objednávky 2, 4, 6,... jsou aktuálně podporovány.</span><span class="sxs-lookup"><span data-stu-id="6aedb-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="6aedb-114">Výstup: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="6aedb-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6aedb-115">Vrátí jednotnou implementaci integrátoru Trotter – Suzuki, kde první parametr `Double` je velikost kroku integrace, a druhý parametr je cílem, na kterém se pracuje.</span><span class="sxs-lookup"><span data-stu-id="6aedb-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6aedb-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6aedb-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6aedb-117">'S</span><span class="sxs-lookup"><span data-stu-id="6aedb-117">'T</span></span>

<span data-ttu-id="6aedb-118">Typ, na který má každý krok reagovat; obvykle buď `Qubit[]` nebo `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="6aedb-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6aedb-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6aedb-119">Remarks</span></span>

<span data-ttu-id="6aedb-120">Při volání s `order` hodnotou Equal `1` vrátí tato funkce operaci, kterou lze simulovat pomocí nejnižšího řádu Trotter – Suzuki integrátor $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $ tam, kde jsme následovali zápis [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) a let $ \lambda $ bude časem vývoje (reprezentovaný prvním vstupem vrácené operace), a nechat $ \{ H_j \} _ {j = 1} ^ {m} $ být sadou (zkosit-Hermitian) dynamické generátory, které `op(j, lambda, _)` jsou simulované jednotkovým operátorem $e ^ {H_j \lambda} $.</span><span class="sxs-lookup"><span data-stu-id="6aedb-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="6aedb-121">Podobně vrátí objekt `order` z `2` druhé objednávky symetrický Trotter – Suzuki integrátor $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.</span><span class="sxs-lookup"><span data-stu-id="6aedb-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="6aedb-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="6aedb-122">\end{align} $$</span></span>

<span data-ttu-id="6aedb-123">Vyšší i hodnoty `order` jsou implementovány pomocí rekurzivní konstrukce [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="6aedb-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="6aedb-124">Odkazy</span><span class="sxs-lookup"><span data-stu-id="6aedb-124">References</span></span>

- [<span data-ttu-id="6aedb-125">*D. W. bobulovina, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="6aedb-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)