---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Operace ApplyToFirstThreeQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 5572bd2a096a4f9bdb1153ae80950ae854965b82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217454"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="d8c90-102">Operace ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="d8c90-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="d8c90-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d8c90-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d8c90-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8c90-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8c90-105">Použije operaci na první tři qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="d8c90-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d8c90-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d8c90-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="d8c90-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8c90-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d8c90-108">Operace, která se má použít pro první tři qubits</span><span class="sxs-lookup"><span data-stu-id="d8c90-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="d8c90-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d8c90-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d8c90-110">Qubit pole na první tři qubits, ze kterých se operace používá.</span><span class="sxs-lookup"><span data-stu-id="d8c90-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8c90-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8c90-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d8c90-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d8c90-112">Remarks</span></span>

<span data-ttu-id="d8c90-113">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="d8c90-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="d8c90-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="d8c90-114">See Also</span></span>

- [<span data-ttu-id="d8c90-115">Microsoft. proApplyToFirstThreeQubitsC. Canon.</span><span class="sxs-lookup"><span data-stu-id="d8c90-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="d8c90-116">Microsoft. proApplyToFirstThreeQubitsA. Canon.</span><span class="sxs-lookup"><span data-stu-id="d8c90-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="d8c90-117">Microsoft. proApplyToFirstThreeQubitsCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="d8c90-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)