---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: Operace ApplyToFirstThreeQubitsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bd7a3ac260d370aae9da8691fcd34a8b6221d451
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704841"
---
# <a name="applytofirstthreequbitsca-operation"></a><span data-ttu-id="8a0b8-102">Operace ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="8a0b8-102">ApplyToFirstThreeQubitsCA operation</span></span>

<span data-ttu-id="8a0b8-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8a0b8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8a0b8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a0b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a0b8-105">Použije operaci na první tři qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="8a0b8-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="8a0b8-106">Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.</span><span class="sxs-lookup"><span data-stu-id="8a0b8-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8a0b8-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="8a0b8-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj--ctl"></a><span data-ttu-id="8a0b8-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="8a0b8-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="8a0b8-109">Operace, která se má použít pro první tři qubits</span><span class="sxs-lookup"><span data-stu-id="8a0b8-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="8a0b8-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8a0b8-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8a0b8-111">Qubit pole na první tři qubits, ze kterých se operace používá.</span><span class="sxs-lookup"><span data-stu-id="8a0b8-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8a0b8-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a0b8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8a0b8-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8a0b8-113">Remarks</span></span>

<span data-ttu-id="8a0b8-114">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="8a0b8-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="8a0b8-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="8a0b8-115">See Also</span></span>

- [<span data-ttu-id="8a0b8-116">Microsoft. proApplyToFirstThreeQubits. Canon.</span><span class="sxs-lookup"><span data-stu-id="8a0b8-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)