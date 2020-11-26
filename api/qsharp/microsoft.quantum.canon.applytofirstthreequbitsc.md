---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: Operace ApplyToFirstThreeQubitsC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: cb6945f5aa398d0bf6417c5cfd21142008a54b13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217437"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="1997b-102">Operace ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="1997b-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="1997b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1997b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1997b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1997b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1997b-105">Použije operaci na první tři qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="1997b-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="1997b-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="1997b-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="1997b-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="1997b-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit--is-ctl"></a><span data-ttu-id="1997b-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="1997b-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1997b-109">Operace, která se má použít pro první tři qubits</span><span class="sxs-lookup"><span data-stu-id="1997b-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="1997b-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1997b-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1997b-111">Qubit pole na první tři qubits, ze kterých se operace používá.</span><span class="sxs-lookup"><span data-stu-id="1997b-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1997b-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1997b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1997b-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1997b-113">Remarks</span></span>

<span data-ttu-id="1997b-114">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="1997b-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="1997b-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="1997b-115">See Also</span></span>

- [<span data-ttu-id="1997b-116">Microsoft. proApplyToFirstThreeQubits. Canon.</span><span class="sxs-lookup"><span data-stu-id="1997b-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)