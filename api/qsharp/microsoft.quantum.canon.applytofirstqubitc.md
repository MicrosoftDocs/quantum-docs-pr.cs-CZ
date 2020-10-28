---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Operace ApplyToFirstQubitC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704880"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="372ed-102">Operace ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="372ed-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="372ed-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="372ed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="372ed-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="372ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="372ed-105">Aplikuje operaci op na první qubit v registru.</span><span class="sxs-lookup"><span data-stu-id="372ed-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="372ed-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="372ed-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="372ed-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="372ed-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="372ed-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => CTL pro [jednotky](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="372ed-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="372ed-109">Operace, která se má použít pro první qubit</span><span class="sxs-lookup"><span data-stu-id="372ed-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="372ed-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="372ed-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="372ed-111">Qubit pole na první qubit, ze kterého se operace používá.</span><span class="sxs-lookup"><span data-stu-id="372ed-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="372ed-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="372ed-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="372ed-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="372ed-113">See Also</span></span>

- [<span data-ttu-id="372ed-114">Microsoft. proApplyToFirstQubit. Canon.</span><span class="sxs-lookup"><span data-stu-id="372ed-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)