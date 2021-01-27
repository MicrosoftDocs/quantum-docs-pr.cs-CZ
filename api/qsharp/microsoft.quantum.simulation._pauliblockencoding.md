---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: c27ef1a6b7cd7c84defe2a783e9fb1610e52d1e7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851062"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="dd0c8-102">_PauliBlockEncoding funkce</span><span class="sxs-lookup"><span data-stu-id="dd0c8-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="dd0c8-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="dd0c8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="dd0c8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd0c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd0c8-105">Vytvoří jednotkové kódování bloku pro Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="dd0c8-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="dd0c8-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ je popsána na základě součtu Pauli podmínek $P _j $, každý s reálným koeficientem $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="dd0c8-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="dd0c8-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="dd0c8-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="dd0c8-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="dd0c8-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="dd0c8-109">A `GeneratorSystem` který popisuje $H $ jako součet podmínek Pauli</span><span class="sxs-lookup"><span data-stu-id="dd0c8-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a><span data-ttu-id="dd0c8-110">statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="dd0c8-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dd0c8-111">Jednotková operace $V $, která používá jednotkovou $V _j $ řízenou v indexu $ \ket{j} $, a to s ohledem na funkci $f: j\rightarrow V_j $.</span><span class="sxs-lookup"><span data-stu-id="dd0c8-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="dd0c8-112">multiplexor: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL.</span><span class="sxs-lookup"><span data-stu-id="dd0c8-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="dd0c8-113">Výstup: ([Double](xref:microsoft.quantum.lang-ref.double);[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="dd0c8-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="dd0c8-114">První parametr</span><span class="sxs-lookup"><span data-stu-id="dd0c8-114">First parameter</span></span>

<span data-ttu-id="dd0c8-115">Jedna-norma koeficientů $ \Alpha = \ sum_ {j} | \ alpha_j | $</span><span class="sxs-lookup"><span data-stu-id="dd0c8-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="dd0c8-116">Druhý parametr</span><span class="sxs-lookup"><span data-stu-id="dd0c8-116">Second parameter</span></span>

<span data-ttu-id="dd0c8-117">`BlockEncodingReflection`Jednotková $U $ $U Hamiltonian $.</span><span class="sxs-lookup"><span data-stu-id="dd0c8-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="dd0c8-118">Protože tato jednotná operace splňuje $U ^ 2 = I $, je také odraz.</span><span class="sxs-lookup"><span data-stu-id="dd0c8-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd0c8-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dd0c8-119">Remarks</span></span>

<span data-ttu-id="dd0c8-120">Příklady operací, které připravují a odstavují stav $ \ sum_ {j}, alpha_j/\Alpha}\ket{j} $, a vytvoří jednotkovou jednotně řízenou hodnotou <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> a <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="dd0c8-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>