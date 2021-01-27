---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Operace PrepareUniformSuperposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854320"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="5fa07-102">Operace PrepareUniformSuperposition</span><span class="sxs-lookup"><span data-stu-id="5fa07-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="5fa07-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="5fa07-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="5fa07-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fa07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fa07-105">Vytvoří jednotnou polohu přes stavy, které zakódují 0 do `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="5fa07-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="5fa07-106">To znamená, že tato Jednotková $U $ vytvoří jednotnou polohu ve všech číselných stavech $0 $ to $M-$1 a zadá vstupní stav $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="5fa07-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="5fa07-107">Jinými slovy $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="5fa07-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="5fa07-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="5fa07-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5fa07-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="5fa07-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="5fa07-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5fa07-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5fa07-111">Požadovaný počet stavů $M $ v jednotném umístění.</span><span class="sxs-lookup"><span data-stu-id="5fa07-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="5fa07-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5fa07-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5fa07-113">Registr qubit, ve kterém se ukládají číselné stavy ve `LittleEndian` formátu</span><span class="sxs-lookup"><span data-stu-id="5fa07-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="5fa07-114">Tento registr musí být schopný ukládat číslo $M-$1 a předpokládá se, že bude inicializovaný ve stavu $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="5fa07-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5fa07-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fa07-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="5fa07-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="5fa07-116">Example</span></span>

<span data-ttu-id="5fa07-117">Následující příklad připraví stav $ \frac {1} {\sqrt {6} } \ sum_ {j = 0} ^ {5} \ket{j} $ na $3 $ qubits.</span><span class="sxs-lookup"><span data-stu-id="5fa07-117">The following example prepares the state $\frac{1}{\sqrt{6}}\sum_{j=0}^{5}\ket{j}$ on $3$ qubits.</span></span>

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a><span data-ttu-id="5fa07-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5fa07-118">Remarks</span></span>

<span data-ttu-id="5fa07-119">Tato operace je typu sousední, ale vyžaduje, aby v takovém `indexRegister` případě byla v jednotném stavu v rámci prvního `nIndices` základu.</span><span class="sxs-lookup"><span data-stu-id="5fa07-119">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>