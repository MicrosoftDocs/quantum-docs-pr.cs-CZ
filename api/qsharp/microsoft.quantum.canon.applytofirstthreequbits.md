---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Operace ApplyToFirstThreeQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: b01c1072306cfdebcb90827a14683a32312481fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850702"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="f8fa8-102">Operace ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="f8fa8-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="f8fa8-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f8fa8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f8fa8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8fa8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8fa8-105">Použije operaci na první tři qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="f8fa8-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f8fa8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f8fa8-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="f8fa8-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8fa8-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f8fa8-108">Operace, která se má použít pro první tři qubits</span><span class="sxs-lookup"><span data-stu-id="f8fa8-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f8fa8-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f8fa8-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f8fa8-110">Qubit pole na první tři qubits, ze kterých se operace používá.</span><span class="sxs-lookup"><span data-stu-id="f8fa8-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8fa8-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8fa8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f8fa8-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f8fa8-112">Remarks</span></span>

<span data-ttu-id="f8fa8-113">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="f8fa8-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="f8fa8-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="f8fa8-114">See Also</span></span>

- [<span data-ttu-id="f8fa8-115">Microsoft. proApplyToFirstThreeQubitsC. Canon.</span><span class="sxs-lookup"><span data-stu-id="f8fa8-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="f8fa8-116">Microsoft. proApplyToFirstThreeQubitsA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f8fa8-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="f8fa8-117">Microsoft. proApplyToFirstThreeQubitsCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f8fa8-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)