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
# <a name="assertqubitisinstatewithintolerance-operation"></a>Operace AssertQubitIsInStateWithinTolerance

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vyhodnotí, že qubit v očekávaném stavu.

`expected` představuje složitý vektor, $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.
První prvek řazených kolekcí členů, který představuje každý z $a $, $b $ je reálnou částí komplexního čísla, zatímco druhým z nich je imaginární část.
Poslední argument definuje toleranci, se kterou je proveden kontrolní výraz.

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Vstup

### <a name="expected--complexcomplex"></a>očekáváno: ([komplexní](xref:Microsoft.Quantum.Math.Complex),[komplexní](xref:Microsoft.Quantum.Math.Complex))

Očekávala se složitá amplituda pro $ \ket {0} $ a $ \ket {1} $ v uvedeném pořadí.


### <a name="register--qubit"></a>registrovat: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, jehož stav má být uplatněn. Všimněte si, že tento qubit se předpokládá, že se bude dělit od ostatních přidělených qubits a ne entangled.


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Aditivní tolerance, pomocí které mají skutečné amplitudy povolenou odchylku od očekávaného.
Podrobnosti najdete níže v části poznámky.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Příklad

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

## <a name="remarks"></a>Poznámky

Následující kód Mathematica lze použít k ověření výrazů pro mi, MX, my, MZ:

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

Tolerance je $L \_ {\infty} $ Distance mezi 3 multidimenzionálním skutečným vektorem (x ₂, x ₃, x ₄) definované pomocí $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ a reálného vektoru (y ₂, y ₃, y ₄) definované ρ = y ₁ I + y ₂ x + y ₃ Y + y ₄ Z, kde ρ je matice hustoty odpovídající stavu registru.
To platí pouze za předpokladu, že tr (ρ) a tr (| ψ ⟩ ⟨ ψ |) jsou obě 1 (například x ₁ = 1/2, y ₁ = 1/2).
Pokud se nejedná o tento případ, funkce vyhodnotí, že l ∞á vzdálenost mezi (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) a (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) je menší než parametr tolerance.