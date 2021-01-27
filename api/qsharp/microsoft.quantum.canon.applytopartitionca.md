---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: Operace ApplyToPartitionCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 572cf824647b3e7f7c0e17c797d519f41914f79d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841286"
---
# <a name="applytopartitionca-operation"></a><span data-ttu-id="3954a-102">Operace ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="3954a-102">ApplyToPartitionCA operation</span></span>

<span data-ttu-id="3954a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3954a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3954a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3954a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3954a-105">Aplikuje dvojici operací na daný oddíl registru do dvou částí.</span><span class="sxs-lookup"><span data-stu-id="3954a-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="3954a-106">Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.</span><span class="sxs-lookup"><span data-stu-id="3954a-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3954a-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="3954a-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="3954a-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="3954a-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="3954a-109">Dvojice operací, které mají být pro daný oddíl aplikovány.</span><span class="sxs-lookup"><span data-stu-id="3954a-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="3954a-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3954a-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3954a-111">Počet qubits z cíle na vložení do první části oddílu</span><span class="sxs-lookup"><span data-stu-id="3954a-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="3954a-112">Zbývající qubits tvoří druhou část oddílu.</span><span class="sxs-lookup"><span data-stu-id="3954a-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3954a-113">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3954a-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3954a-114">Registr qubitsů, které jsou rozděleny na oddíly a provozovány na základě dané dvě operace.</span><span class="sxs-lookup"><span data-stu-id="3954a-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3954a-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3954a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3954a-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="3954a-116">See Also</span></span>

- [<span data-ttu-id="3954a-117">Microsoft. proApplyToPartition. Canon.</span><span class="sxs-lookup"><span data-stu-id="3954a-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)