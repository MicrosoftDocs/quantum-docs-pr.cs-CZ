---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: Operace ApplyToPartitionC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 840c93c653d71af1a82fb0dc51d9e056176ba88b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704712"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="0c963-102">Operace ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="0c963-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="0c963-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0c963-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0c963-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c963-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c963-105">Aplikuje dvojici operací na daný oddíl registru do dvou částí.</span><span class="sxs-lookup"><span data-stu-id="0c963-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="0c963-106">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="0c963-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0c963-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="0c963-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="0c963-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) [=> CTL](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c963-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0c963-109">Dvojice operací, které mají být pro daný oddíl aplikovány.</span><span class="sxs-lookup"><span data-stu-id="0c963-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="0c963-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0c963-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0c963-111">Počet qubits z cíle na vložení do první části oddílu</span><span class="sxs-lookup"><span data-stu-id="0c963-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="0c963-112">Zbývající qubits tvoří druhou část oddílu.</span><span class="sxs-lookup"><span data-stu-id="0c963-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0c963-113">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0c963-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0c963-114">Registr qubitsů, které jsou rozděleny na oddíly a provozovány na základě dané dvě operace.</span><span class="sxs-lookup"><span data-stu-id="0c963-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c963-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c963-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0c963-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="0c963-116">See Also</span></span>

- [<span data-ttu-id="0c963-117">Microsoft. proApplyToPartition. Canon.</span><span class="sxs-lookup"><span data-stu-id="0c963-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)