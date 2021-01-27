---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operace AssertMeasurementProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830822"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="e4d36-102">Operace AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="e4d36-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="e4d36-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e4d36-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e4d36-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e4d36-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e4d36-105">Vyhodnotí, že měření daného qubits v daném Pauli základu bude mít daný výsledek s danou pravděpodobností v rámci určité tolerance.</span><span class="sxs-lookup"><span data-stu-id="e4d36-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e4d36-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e4d36-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="e4d36-107">základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e4d36-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="e4d36-108">Měřicí efekt pro vyhodnocení pravděpodobnosti vyjádřené jako qubit Pauli operátor.</span><span class="sxs-lookup"><span data-stu-id="e4d36-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e4d36-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4d36-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e4d36-110">Registr, na který se má kontrolní výraz provést.</span><span class="sxs-lookup"><span data-stu-id="e4d36-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="e4d36-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="e4d36-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="e4d36-112">Očekávaný výsledek `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="e4d36-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="e4d36-113">test: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e4d36-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e4d36-114">Pravděpodobnost, se kterou se očekává daný výsledek.</span><span class="sxs-lookup"><span data-stu-id="e4d36-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="e4d36-115">Msg: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e4d36-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e4d36-116">Zpráva, která má být hlášena v případě, že se kontrolní výraz nezdařil.</span><span class="sxs-lookup"><span data-stu-id="e4d36-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="e4d36-117">Typ platby: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e4d36-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="e4d36-118">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4d36-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="e4d36-119">Příklad</span><span class="sxs-lookup"><span data-stu-id="e4d36-119">Example</span></span>

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="e4d36-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e4d36-120">Remarks</span></span>

<span data-ttu-id="e4d36-121">Všimněte si, že sousední a kontrolované verze této operace nekontrolují podmínku.</span><span class="sxs-lookup"><span data-stu-id="e4d36-121">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4d36-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="e4d36-122">See Also</span></span>

- [<span data-ttu-id="e4d36-123">Microsoft. AssertMeasurement. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="e4d36-123">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)