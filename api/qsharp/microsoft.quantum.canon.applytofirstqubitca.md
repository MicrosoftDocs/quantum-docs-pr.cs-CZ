---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Operace ApplyToFirstQubitCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704872"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="b0762-102">Operace ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="b0762-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="b0762-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b0762-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b0762-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b0762-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b0762-105">Aplikuje operaci op na první qubit v registru.</span><span class="sxs-lookup"><span data-stu-id="b0762-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="b0762-106">Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.</span><span class="sxs-lookup"><span data-stu-id="b0762-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b0762-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="b0762-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="b0762-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="b0762-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b0762-109">Operace, která se má použít pro první qubit</span><span class="sxs-lookup"><span data-stu-id="b0762-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="b0762-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b0762-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b0762-111">Qubit pole na první qubit, ze kterého se operace používá.</span><span class="sxs-lookup"><span data-stu-id="b0762-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0762-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0762-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b0762-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="b0762-113">See Also</span></span>

- [<span data-ttu-id="b0762-114">Microsoft. proApplyToFirstQubit. Canon.</span><span class="sxs-lookup"><span data-stu-id="b0762-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)