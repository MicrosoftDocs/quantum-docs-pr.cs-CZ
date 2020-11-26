---
uid: Microsoft.Quantum.Intrinsic.M
title: M operace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: ced3a617a7299e169c7a58a1cd0f83f656b2f0b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212337"
---
# <a name="m-operation"></a><span data-ttu-id="a4a0c-102">M operace</span><span class="sxs-lookup"><span data-stu-id="a4a0c-102">M operation</span></span>

<span data-ttu-id="a4a0c-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a4a0c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a4a0c-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a4a0c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a4a0c-105">Provede měření jediného qubitu v Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="a4a0c-106">Výsledek výstupu je dán distribucí \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="a4a0c-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a4a0c-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="a4a0c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="a4a0c-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="a4a0c-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a4a0c-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a4a0c-110">Qubit k měření.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a4a0c-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="a4a0c-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="a4a0c-112">`Zero` Pokud se eigenvalue $ + $1, a `One` Pokud je zjištěna $-$1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4a0c-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a4a0c-113">Remarks</span></span>

<span data-ttu-id="a4a0c-114">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="a4a0c-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```