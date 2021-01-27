---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Operace AssertQubit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853453"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="5c24c-102">Operace AssertQubit</span><span class="sxs-lookup"><span data-stu-id="5c24c-102">AssertQubit operation</span></span>

<span data-ttu-id="5c24c-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5c24c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5c24c-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5c24c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5c24c-105">Vyhodnotí, že qubit `q` je v očekávané eigenstate operátoru Pauli z.</span><span class="sxs-lookup"><span data-stu-id="5c24c-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5c24c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5c24c-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="5c24c-107">očekáváno __: <Result> neplatné__</span><span class="sxs-lookup"><span data-stu-id="5c24c-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="5c24c-108">Který stav qubit má být v: `Zero` nebo `One` .</span><span class="sxs-lookup"><span data-stu-id="5c24c-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="5c24c-109">Otázka: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5c24c-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5c24c-110">Qubit, jehož stav je uplatněn.</span><span class="sxs-lookup"><span data-stu-id="5c24c-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c24c-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c24c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5c24c-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5c24c-112">Remarks</span></span>

<span data-ttu-id="5c24c-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umožňuje vyhodnotit libovolný stav qubit spíše než jenom $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="5c24c-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c24c-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="5c24c-114">See Also</span></span>

- [<span data-ttu-id="5c24c-115">Microsoft. AssertQubitIsInStateWithinTolerance. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="5c24c-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)