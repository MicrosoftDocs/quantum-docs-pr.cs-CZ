---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Operace PrepareUniformSuperposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697148"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="f9d9b-102">Operace PrepareUniformSuperposition</span><span class="sxs-lookup"><span data-stu-id="f9d9b-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="f9d9b-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f9d9b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f9d9b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9d9b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9d9b-105">Vytvoří jednotnou polohu přes stavy, které zakódují 0 do `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="f9d9b-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="f9d9b-106">To znamená, že tato Jednotková $U $ vytvoří jednotnou polohu ve všech číselných stavech $0 $ to $M-$1 a zadá vstupní stav $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="f9d9b-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="f9d9b-107">Jinými slovy $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="f9d9b-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="f9d9b-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="f9d9b-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="f9d9b-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="f9d9b-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="f9d9b-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9d9b-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9d9b-111">Požadovaný počet stavů $M $ v jednotném umístění.</span><span class="sxs-lookup"><span data-stu-id="f9d9b-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="f9d9b-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f9d9b-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f9d9b-113">Registr qubit, ve kterém se ukládají číselné stavy ve `LittleEndian` formátu</span><span class="sxs-lookup"><span data-stu-id="f9d9b-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="f9d9b-114">Tento registr musí být schopný ukládat číslo $M-$1 a předpokládá se, že bude inicializovaný ve stavu $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="f9d9b-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9d9b-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9d9b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f9d9b-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f9d9b-116">Remarks</span></span>

<span data-ttu-id="f9d9b-117">Tato operace je typu sousední, ale vyžaduje, aby v takovém `indexRegister` případě byla v jednotném stavu v rámci prvního `nIndices` základu.</span><span class="sxs-lookup"><span data-stu-id="f9d9b-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>