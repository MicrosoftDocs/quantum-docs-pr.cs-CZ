---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: Operace ApplyToFirstThreeQubitsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 9450b084cd77f75511fe631cda9a4f9fc426142d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704857"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="d223c-102">Operace ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="d223c-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="d223c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d223c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d223c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d223c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d223c-105">Použije operaci na první tři qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="d223c-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="d223c-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="d223c-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d223c-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d223c-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-ctl"></a><span data-ttu-id="d223c-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = seznam CTL pro> [jednotku](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d223c-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="d223c-109">Operace, která se má použít pro první tři qubits</span><span class="sxs-lookup"><span data-stu-id="d223c-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="d223c-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d223c-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d223c-111">Qubit pole na první tři qubits, ze kterých se operace používá.</span><span class="sxs-lookup"><span data-stu-id="d223c-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d223c-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d223c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d223c-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d223c-113">Remarks</span></span>

<span data-ttu-id="d223c-114">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="d223c-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="d223c-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="d223c-115">See Also</span></span>

- [<span data-ttu-id="d223c-116">Microsoft. proApplyToFirstThreeQubits. Canon.</span><span class="sxs-lookup"><span data-stu-id="d223c-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)