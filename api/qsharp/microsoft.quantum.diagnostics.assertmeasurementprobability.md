---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operace AssertMeasurementProbability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202358"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="ecaa1-102">Operace AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="ecaa1-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="ecaa1-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ecaa1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ecaa1-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ecaa1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ecaa1-105">Vyhodnotí, že měření daného qubits v daném Pauli základu bude mít daný výsledek s danou pravděpodobností v rámci určité tolerance.</span><span class="sxs-lookup"><span data-stu-id="ecaa1-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ecaa1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ecaa1-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="ecaa1-107">základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ecaa1-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ecaa1-108">Měřicí efekt pro vyhodnocení pravděpodobnosti vyjádřené jako qubit Pauli operátor.</span><span class="sxs-lookup"><span data-stu-id="ecaa1-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ecaa1-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ecaa1-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ecaa1-110">Registr, na který se má kontrolní výraz provést.</span><span class="sxs-lookup"><span data-stu-id="ecaa1-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="ecaa1-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="ecaa1-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="ecaa1-112">Očekávaný výsledek `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="ecaa1-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="ecaa1-113">test: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ecaa1-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ecaa1-114">Pravděpodobnost, se kterou se očekává daný výsledek.</span><span class="sxs-lookup"><span data-stu-id="ecaa1-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="ecaa1-115">Msg: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ecaa1-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ecaa1-116">Zpráva, která má být hlášena v případě, že se kontrolní výraz nezdařil.</span><span class="sxs-lookup"><span data-stu-id="ecaa1-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="ecaa1-117">Typ platby: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ecaa1-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="ecaa1-118">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ecaa1-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ecaa1-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ecaa1-119">Remarks</span></span>

<span data-ttu-id="ecaa1-120">Všimněte si, že sousední a kontrolované verze této operace nekontrolují podmínku.</span><span class="sxs-lookup"><span data-stu-id="ecaa1-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecaa1-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="ecaa1-121">See Also</span></span>

- [<span data-ttu-id="ecaa1-122">Microsoft. AssertMeasurement. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="ecaa1-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)