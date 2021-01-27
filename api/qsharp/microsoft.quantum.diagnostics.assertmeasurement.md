---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operace AssertMeasurement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853501"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="dd574-102">Operace AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="dd574-102">AssertMeasurement operation</span></span>

<span data-ttu-id="dd574-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="dd574-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="dd574-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dd574-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dd574-105">Vyhodnotí, že měření daného qubits v dané Pauli základu bude mít vždy daný výsledek.</span><span class="sxs-lookup"><span data-stu-id="dd574-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dd574-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="dd574-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="dd574-107">základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="dd574-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="dd574-108">Měřicí efekt pro vyhodnocení pravděpodobnosti vyjádřené jako qubit Pauli operátor.</span><span class="sxs-lookup"><span data-stu-id="dd574-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="dd574-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dd574-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dd574-110">Registr, na který se má kontrolní výraz provést.</span><span class="sxs-lookup"><span data-stu-id="dd574-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="dd574-111">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="dd574-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="dd574-112">Očekávaný výsledek `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="dd574-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="dd574-113">Msg: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="dd574-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="dd574-114">Zpráva, která má být hlášena v případě, že se kontrolní výraz nezdařil.</span><span class="sxs-lookup"><span data-stu-id="dd574-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd574-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd574-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dd574-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dd574-116">Remarks</span></span>

<span data-ttu-id="dd574-117">Všimněte si, že sousední a kontrolované verze této operace nekontrolují podmínku.</span><span class="sxs-lookup"><span data-stu-id="dd574-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd574-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="dd574-118">See Also</span></span>

- [<span data-ttu-id="dd574-119">Microsoft. AssertMeasurementProbability. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="dd574-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)