---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: Operace ApplyToSubregisterC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 52564e64d8cc9cdbeb2626ed8694168b8ed48c22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850462"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="2e6f8-102">Operace ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="2e6f8-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="2e6f8-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2e6f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2e6f8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e6f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e6f8-105">Aplikuje operaci na subregistry registru, kde qubits určil pole jeho indexů.</span><span class="sxs-lookup"><span data-stu-id="2e6f8-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="2e6f8-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="2e6f8-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="2e6f8-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="2e6f8-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="2e6f8-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="2e6f8-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2e6f8-109">Operace, která se má použít pro podregistr</span><span class="sxs-lookup"><span data-stu-id="2e6f8-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="2e6f8-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2e6f8-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2e6f8-111">Pole indexů, která označují, která qubits se operace použije.</span><span class="sxs-lookup"><span data-stu-id="2e6f8-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2e6f8-112">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2e6f8-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2e6f8-113">Zaregistrujte, na které operace funguje.</span><span class="sxs-lookup"><span data-stu-id="2e6f8-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e6f8-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e6f8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2e6f8-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="2e6f8-115">See Also</span></span>

- [<span data-ttu-id="2e6f8-116">Microsoft. proApplyToSubregister. Canon.</span><span class="sxs-lookup"><span data-stu-id="2e6f8-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)