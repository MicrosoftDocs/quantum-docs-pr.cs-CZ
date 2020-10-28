---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: Operace ApplyToFirstTwoQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: aad07889c0dbf2329304c98b06dbd0c225df8a81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704824"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="4a105-102">Operace ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="4a105-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="4a105-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a105-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a105-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a105-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a105-105">Použije operaci na první dvě qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="4a105-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="4a105-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4a105-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="4a105-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a105-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4a105-108">Operace, která se má použít pro první dvě qubits</span><span class="sxs-lookup"><span data-stu-id="4a105-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="4a105-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4a105-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4a105-110">Qubit pole na první dvě qubits, z nichž je operace použita.</span><span class="sxs-lookup"><span data-stu-id="4a105-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a105-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a105-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4a105-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4a105-112">Remarks</span></span>

<span data-ttu-id="4a105-113">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="4a105-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="4a105-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="4a105-114">See Also</span></span>

- [<span data-ttu-id="4a105-115">Microsoft. proApplyToFirstTwoQubitsA. Canon.</span><span class="sxs-lookup"><span data-stu-id="4a105-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="4a105-116">Microsoft. proApplyToFirstTwoQubitsC. Canon.</span><span class="sxs-lookup"><span data-stu-id="4a105-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="4a105-117">Microsoft. proApplyToFirstTwoQubitsCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="4a105-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)