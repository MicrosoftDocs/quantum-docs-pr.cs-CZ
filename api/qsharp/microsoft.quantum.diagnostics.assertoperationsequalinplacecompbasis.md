---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: Operace AssertOperationsEqualInPlaceCompBasis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698149"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="b1ce3-102">Operace AssertOperationsEqualInPlaceCompBasis</span><span class="sxs-lookup"><span data-stu-id="b1ce3-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="b1ce3-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b1ce3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b1ce3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1ce3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1ce3-105">Kontroluje `givenU` , zda je operace shodná s operací `expectedU` na dané vstupní velikosti tím, že kontroluje akci operací pouze na vektorech z výpočetního základu.</span><span class="sxs-lookup"><span data-stu-id="b1ce3-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="b1ce3-106">To je nezbytné, ale nedostatečné, podmínkou rovnosti dvou unitaries.</span><span class="sxs-lookup"><span data-stu-id="b1ce3-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="b1ce3-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="b1ce3-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b1ce3-108">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1ce3-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1ce3-109">Počet qubits $n $, na kterých operace `givenU` fungují a `expectedU` pracují.</span><span class="sxs-lookup"><span data-stu-id="b1ce3-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="b1ce3-110">předané: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1ce3-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b1ce3-111">Bude zkontrolována operace na $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="b1ce3-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="b1ce3-112">očekávalo se: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ.</span><span class="sxs-lookup"><span data-stu-id="b1ce3-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="b1ce3-113">Operace reference na $n $ qubits, která se má `givenU` Porovnat s.</span><span class="sxs-lookup"><span data-stu-id="b1ce3-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1ce3-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1ce3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

