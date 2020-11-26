---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Operace ApplyToFirstTwoQubitsC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 6b6ee5f05ace92c15ce2038e2fedbaa2fee3dcc9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217352"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="5335c-102">Operace ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="5335c-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="5335c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5335c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5335c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5335c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5335c-105">Použije operaci na první dvě qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="5335c-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="5335c-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="5335c-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="5335c-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="5335c-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="5335c-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="5335c-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="5335c-109">Operace, která se má použít pro první dvě qubits</span><span class="sxs-lookup"><span data-stu-id="5335c-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="5335c-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5335c-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5335c-111">Qubit pole na první dvě qubits, z nichž je operace použita.</span><span class="sxs-lookup"><span data-stu-id="5335c-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5335c-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5335c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5335c-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5335c-113">Remarks</span></span>

<span data-ttu-id="5335c-114">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="5335c-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="5335c-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="5335c-115">See Also</span></span>

- [<span data-ttu-id="5335c-116">Microsoft. proApplyToFirstTwoQubits. Canon.</span><span class="sxs-lookup"><span data-stu-id="5335c-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)