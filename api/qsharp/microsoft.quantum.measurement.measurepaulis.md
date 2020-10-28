---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Operace MeasurePaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706760"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="94264-102">Operace MeasurePaulis</span><span class="sxs-lookup"><span data-stu-id="94264-102">MeasurePaulis operation</span></span>

<span data-ttu-id="94264-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="94264-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="94264-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94264-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94264-105">V případě pole qubitch operátorů Pauli, měří jednotlivé míry pomocí určené míry měření a vrátí pole výsledků.</span><span class="sxs-lookup"><span data-stu-id="94264-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="94264-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="94264-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="94264-107">Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="94264-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="94264-108">Pole qubitch Paulich operátorů k měření.</span><span class="sxs-lookup"><span data-stu-id="94264-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="94264-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="94264-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="94264-110">Zaregistrujte, na které se mají měřit dané operátory.</span><span class="sxs-lookup"><span data-stu-id="94264-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="94264-111">gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]; [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="94264-111">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="94264-112">Operace, která provádí měření daného qubit operátoru.</span><span class="sxs-lookup"><span data-stu-id="94264-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="94264-113">Výstup: __neplatný <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="94264-113">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="94264-114">Pole výsledků získané z měření každého elementu `paulis` v `target` .</span><span class="sxs-lookup"><span data-stu-id="94264-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>