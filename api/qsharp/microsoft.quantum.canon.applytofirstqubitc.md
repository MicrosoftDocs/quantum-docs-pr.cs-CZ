---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Operace ApplyToFirstQubitC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2659c3a97baa68cb4c1d7781381f89742902594d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217505"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="6a485-102">Operace ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="6a485-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="6a485-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a485-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a485-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a485-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a485-105">Aplikuje operaci op na první qubit v registru.</span><span class="sxs-lookup"><span data-stu-id="6a485-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="6a485-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="6a485-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="6a485-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="6a485-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="6a485-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [jednotka](xref:microsoft.quantum.lang-ref.unit) qubit je CTL</span><span class="sxs-lookup"><span data-stu-id="6a485-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6a485-109">Operace, která se má použít pro první qubit</span><span class="sxs-lookup"><span data-stu-id="6a485-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="6a485-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6a485-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6a485-111">Qubit pole na první qubit, ze kterého se operace používá.</span><span class="sxs-lookup"><span data-stu-id="6a485-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a485-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a485-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6a485-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="6a485-113">See Also</span></span>

- [<span data-ttu-id="6a485-114">Microsoft. proApplyToFirstQubit. Canon.</span><span class="sxs-lookup"><span data-stu-id="6a485-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)