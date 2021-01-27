---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: Operace AssertOperationsEqualInPlaceCompBasis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: f9d3aaf7e774cf2495ca69382db2470d1d0fa7b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830482"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="277ae-102">Operace AssertOperationsEqualInPlaceCompBasis</span><span class="sxs-lookup"><span data-stu-id="277ae-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="277ae-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="277ae-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="277ae-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="277ae-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="277ae-105">Kontroluje `givenU` , zda je operace shodná s operací `expectedU` na dané vstupní velikosti tím, že kontroluje akci operací pouze na vektorech z výpočetního základu.</span><span class="sxs-lookup"><span data-stu-id="277ae-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="277ae-106">To je nezbytné, ale nedostatečné, podmínkou rovnosti dvou unitaries.</span><span class="sxs-lookup"><span data-stu-id="277ae-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="277ae-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="277ae-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="277ae-108">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="277ae-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="277ae-109">Počet qubits $n $, na kterých operace `givenU` fungují a `expectedU` pracují.</span><span class="sxs-lookup"><span data-stu-id="277ae-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="277ae-110">předané: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="277ae-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="277ae-111">Bude zkontrolována operace na $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="277ae-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="277ae-112">očekává se: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="277ae-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="277ae-113">Operace reference na $n $ qubits, která se má `givenU` Porovnat s.</span><span class="sxs-lookup"><span data-stu-id="277ae-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="277ae-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="277ae-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

