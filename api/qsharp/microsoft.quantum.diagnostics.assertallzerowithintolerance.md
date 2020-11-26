---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Operace AssertAllZeroWithinTolerance
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: a2e73bbc8949b3cdb7733cfc8aae35680e54d2cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202477"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="af5e7-102">Operace AssertAllZeroWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="af5e7-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="af5e7-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="af5e7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="af5e7-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="af5e7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="af5e7-105">Vyhodnocení, že zadané qubits jsou všechny ve stavu $ \ket {0} $ až do dané tolerance.</span><span class="sxs-lookup"><span data-stu-id="af5e7-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="af5e7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="af5e7-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="af5e7-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="af5e7-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="af5e7-108">Qubits, které jsou uplatněny ve stavu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="af5e7-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="af5e7-109">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="af5e7-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="af5e7-110">Přesnost, se kterou má být stav ve stavu $ \ket {0} $</span><span class="sxs-lookup"><span data-stu-id="af5e7-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="af5e7-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af5e7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="af5e7-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="af5e7-112">See Also</span></span>

- [<span data-ttu-id="af5e7-113">Microsoft. AssertQubitWithinTolerance. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="af5e7-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)