---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698353"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="6194a-102">MeasurementOperators – funkce</span><span class="sxs-lookup"><span data-stu-id="6194a-102">MeasurementOperators function</span></span>

<span data-ttu-id="6194a-103">Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="6194a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="6194a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6194a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6194a-105">Vypočítá všechny operátory měření potřebné k výpočtu očekávaného Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="6194a-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="6194a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6194a-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="6194a-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6194a-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6194a-108">Počet qubits potřebných pro simulaci molekulárního systému.</span><span class="sxs-lookup"><span data-stu-id="6194a-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="6194a-109">indexy: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6194a-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6194a-110">Pole obsahující indexy qubit každý operátor Pauli je aplikován na.</span><span class="sxs-lookup"><span data-stu-id="6194a-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="6194a-111">termType: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6194a-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6194a-112">Typ Jordan-Wigner podmínky.</span><span class="sxs-lookup"><span data-stu-id="6194a-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="6194a-113">Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="6194a-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="6194a-114">Pole operátorů měření (každý z nich je pole Pauli).</span><span class="sxs-lookup"><span data-stu-id="6194a-114">An array of measurement operators (each being an array of Pauli).</span></span>