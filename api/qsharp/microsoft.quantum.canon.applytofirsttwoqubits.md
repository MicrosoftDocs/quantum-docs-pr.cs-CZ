---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: Operace ApplyToFirstTwoQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: e4f1eb396efb390c7470ea2aaf5c3b5be60b8c1b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217403"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="845b3-102">Operace ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="845b3-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="845b3-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="845b3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="845b3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="845b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="845b3-105">Použije operaci na první dvě qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="845b3-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="845b3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="845b3-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="845b3-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="845b3-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="845b3-108">Operace, která se má použít pro první dvě qubits</span><span class="sxs-lookup"><span data-stu-id="845b3-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="845b3-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="845b3-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="845b3-110">Qubit pole na první dvě qubits, z nichž je operace použita.</span><span class="sxs-lookup"><span data-stu-id="845b3-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="845b3-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="845b3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="845b3-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="845b3-112">Remarks</span></span>

<span data-ttu-id="845b3-113">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="845b3-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="845b3-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="845b3-114">See Also</span></span>

- [<span data-ttu-id="845b3-115">Microsoft. proApplyToFirstTwoQubitsA. Canon.</span><span class="sxs-lookup"><span data-stu-id="845b3-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="845b3-116">Microsoft. proApplyToFirstTwoQubitsC. Canon.</span><span class="sxs-lookup"><span data-stu-id="845b3-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="845b3-117">Microsoft. proApplyToFirstTwoQubitsCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="845b3-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)