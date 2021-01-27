---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Operace AssertQubitIsInStateWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829791"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="a3d12-102">Operace AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="a3d12-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="a3d12-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a3d12-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a3d12-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a3d12-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a3d12-105">Vyhodnotí, že qubit v očekávaném stavu.</span><span class="sxs-lookup"><span data-stu-id="a3d12-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="a3d12-106">`expected` představuje složitý vektor, $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.</span><span class="sxs-lookup"><span data-stu-id="a3d12-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="a3d12-107">První prvek řazených kolekcí členů, který představuje každý z $a $, $b $ je reálnou částí komplexního čísla, zatímco druhým z nich je imaginární část.</span><span class="sxs-lookup"><span data-stu-id="a3d12-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="a3d12-108">Poslední argument definuje toleranci, se kterou je proveden kontrolní výraz.</span><span class="sxs-lookup"><span data-stu-id="a3d12-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="a3d12-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="a3d12-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="a3d12-110">očekáváno: ([komplexní](xref:Microsoft.Quantum.Math.Complex),[komplexní](xref:Microsoft.Quantum.Math.Complex))</span><span class="sxs-lookup"><span data-stu-id="a3d12-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="a3d12-111">Očekávala se složitá amplituda pro $ \ket {0} $ a $ \ket {1} $ v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="a3d12-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="a3d12-112">registrovat: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a3d12-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a3d12-113">Qubit, jehož stav má být uplatněn.</span><span class="sxs-lookup"><span data-stu-id="a3d12-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="a3d12-114">Všimněte si, že tento qubit se předpokládá, že se bude dělit od ostatních přidělených qubits a ne entangled.</span><span class="sxs-lookup"><span data-stu-id="a3d12-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="a3d12-115">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a3d12-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a3d12-116">Aditivní tolerance, pomocí které mají skutečné amplitudy povolenou odchylku od očekávaného.</span><span class="sxs-lookup"><span data-stu-id="a3d12-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="a3d12-117">Podrobnosti najdete níže v části poznámky.</span><span class="sxs-lookup"><span data-stu-id="a3d12-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3d12-118">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3d12-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="a3d12-119">Příklad</span><span class="sxs-lookup"><span data-stu-id="a3d12-119">Example</span></span>

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="a3d12-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a3d12-120">Remarks</span></span>

<span data-ttu-id="a3d12-121">Následující kód Mathematica lze použít k ověření výrazů pro mi, MX, my, MZ:</span><span class="sxs-lookup"><span data-stu-id="a3d12-121">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="a3d12-122">Tolerance je $L \_ {\infty} $ Distance mezi 3 multidimenzionálním skutečným vektorem (x ₂, x ₃, x ₄) definované pomocí $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ a reálného vektoru (y ₂, y ₃, y ₄) definované ρ = y ₁ I + y ₂ x + y ₃ Y + y ₄ Z, kde ρ je matice hustoty odpovídající stavu registru.</span><span class="sxs-lookup"><span data-stu-id="a3d12-122">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="a3d12-123">To platí pouze za předpokladu, že tr (ρ) a tr (| ψ ⟩ ⟨ ψ |) jsou obě 1 (například x ₁ = 1/2, y ₁ = 1/2).</span><span class="sxs-lookup"><span data-stu-id="a3d12-123">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="a3d12-124">Pokud se nejedná o tento případ, funkce vyhodnotí, že l ∞á vzdálenost mezi (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) a (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) je menší než parametr tolerance.</span><span class="sxs-lookup"><span data-stu-id="a3d12-124">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>