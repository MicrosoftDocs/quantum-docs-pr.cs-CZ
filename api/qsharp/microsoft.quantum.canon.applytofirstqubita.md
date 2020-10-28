---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Operace ApplyToFirstQubitA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704873"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="03d69-102">Operace ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="03d69-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="03d69-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="03d69-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="03d69-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03d69-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03d69-105">Použije operaci na první qubit v registru.</span><span class="sxs-lookup"><span data-stu-id="03d69-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="03d69-106">Modifikátor `A` označuje, že operace je sousední.</span><span class="sxs-lookup"><span data-stu-id="03d69-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="03d69-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="03d69-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="03d69-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [jednotek](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="03d69-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="03d69-109">Operace, která se má použít pro první qubit</span><span class="sxs-lookup"><span data-stu-id="03d69-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="03d69-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="03d69-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="03d69-111">Qubit pole na první qubit, ze kterého se operace používá.</span><span class="sxs-lookup"><span data-stu-id="03d69-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="03d69-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03d69-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="03d69-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="03d69-113">See Also</span></span>

- [<span data-ttu-id="03d69-114">Microsoft. proApplyToFirstQubit. Canon.</span><span class="sxs-lookup"><span data-stu-id="03d69-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)