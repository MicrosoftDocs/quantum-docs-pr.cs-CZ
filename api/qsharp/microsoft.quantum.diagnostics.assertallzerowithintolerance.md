---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Operace AssertAllZeroWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698172"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="6024c-102">Operace AssertAllZeroWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="6024c-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="6024c-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6024c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6024c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6024c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6024c-105">Vyhodnocení, že zadané qubits jsou všechny ve stavu $ \ket {0} $ až do dané tolerance.</span><span class="sxs-lookup"><span data-stu-id="6024c-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="6024c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6024c-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="6024c-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6024c-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6024c-108">Qubits, které jsou uplatněny ve stavu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="6024c-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="6024c-109">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6024c-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6024c-110">Přesnost, se kterou má být stav ve stavu $ \ket {0} $</span><span class="sxs-lookup"><span data-stu-id="6024c-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="6024c-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6024c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6024c-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="6024c-112">See Also</span></span>

- [<span data-ttu-id="6024c-113">Microsoft. AssertQubitWithinTolerance. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="6024c-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)