---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Operace ApplyToFirstThreeQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704864"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="6ca10-102">Operace ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="6ca10-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="6ca10-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6ca10-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6ca10-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ca10-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ca10-105">Použije operaci na první tři qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="6ca10-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6ca10-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6ca10-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="6ca10-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ca10-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6ca10-108">Operace, která se má použít pro první tři qubits</span><span class="sxs-lookup"><span data-stu-id="6ca10-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="6ca10-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6ca10-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6ca10-110">Qubit pole na první tři qubits, ze kterých se operace používá.</span><span class="sxs-lookup"><span data-stu-id="6ca10-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ca10-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ca10-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6ca10-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6ca10-112">Remarks</span></span>

<span data-ttu-id="6ca10-113">Jedná se o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="6ca10-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="6ca10-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="6ca10-114">See Also</span></span>

- [<span data-ttu-id="6ca10-115">Microsoft. proApplyToFirstThreeQubitsC. Canon.</span><span class="sxs-lookup"><span data-stu-id="6ca10-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="6ca10-116">Microsoft. proApplyToFirstThreeQubitsA. Canon.</span><span class="sxs-lookup"><span data-stu-id="6ca10-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="6ca10-117">Microsoft. proApplyToFirstThreeQubitsCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="6ca10-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)