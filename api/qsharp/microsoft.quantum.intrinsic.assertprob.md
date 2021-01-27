---
uid: Microsoft.Quantum.Intrinsic.AssertProb
title: Operace AssertProb
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: AssertProb
qsharp.summary: >-
  > [!WARNING]

  > AssertProb has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.
ms.openlocfilehash: a3bdf8d6ae64f0d462da1781a723b27b6e1db05e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849456"
---
# <a name="assertprob-operation"></a><span data-ttu-id="5f8cc-102">Operace AssertProb</span><span class="sxs-lookup"><span data-stu-id="5f8cc-102">AssertProb operation</span></span>

<span data-ttu-id="5f8cc-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5f8cc-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5f8cc-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5f8cc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="5f8cc-105">AssertProb se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="5f8cc-105">AssertProb has been deprecated.</span></span> <span data-ttu-id="5f8cc-106"><xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="5f8cc-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.</span></span>



```qsharp
operation AssertProb (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5f8cc-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="5f8cc-107">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="5f8cc-108">základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="5f8cc-108">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="5f8cc-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5f8cc-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="result--__invalidresult__"></a><span data-ttu-id="5f8cc-110">výsledek: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="5f8cc-110">result : __invalid<Result>__</span></span>




### <a name="prob--double"></a><span data-ttu-id="5f8cc-111">test: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5f8cc-111">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="msg--string"></a><span data-ttu-id="5f8cc-112">Msg: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5f8cc-112">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>




### <a name="tol--double"></a><span data-ttu-id="5f8cc-113">Typ platby: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5f8cc-113">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="5f8cc-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5f8cc-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

