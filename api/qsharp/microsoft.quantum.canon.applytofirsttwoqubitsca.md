---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: Operace ApplyToFirstTwoQubitsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 0c5e29fbca8449f8122f2a9f988797e94e27da60
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704793"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="81ce1-102">Operace ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="81ce1-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="81ce1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="81ce1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="81ce1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81ce1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81ce1-105">Použije operaci na první dvě qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="81ce1-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="81ce1-106">Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.</span><span class="sxs-lookup"><span data-stu-id="81ce1-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="81ce1-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="81ce1-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="81ce1-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="81ce1-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="81ce1-109">Operace, která se má použít pro první dvě qubits</span><span class="sxs-lookup"><span data-stu-id="81ce1-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="81ce1-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="81ce1-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="81ce1-111">Qubit pole na první dvě qubits, z nichž je operace použita.</span><span class="sxs-lookup"><span data-stu-id="81ce1-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81ce1-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81ce1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="81ce1-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="81ce1-113">Remarks</span></span>

<span data-ttu-id="81ce1-114">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="81ce1-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="81ce1-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="81ce1-115">See Also</span></span>

- [<span data-ttu-id="81ce1-116">Microsoft. proApplyToFirstTwoQubits. Canon.</span><span class="sxs-lookup"><span data-stu-id="81ce1-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)