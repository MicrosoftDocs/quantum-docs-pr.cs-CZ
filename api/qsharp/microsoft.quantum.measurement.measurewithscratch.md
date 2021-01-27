---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Operace MeasureWithScratch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854662"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="0d7b4-102">Operace MeasureWithScratch</span><span class="sxs-lookup"><span data-stu-id="0d7b4-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="0d7b4-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="0d7b4-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="0d7b4-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d7b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d7b4-105">Měří zadaný Pauli operátor pomocí explicitního qubitho škrábance k provedení měření.</span><span class="sxs-lookup"><span data-stu-id="0d7b4-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="0d7b4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0d7b4-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="0d7b4-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="0d7b4-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="0d7b4-108">Qubit Pauli operátor, který jste zadali jako pole operátorů s jedním qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="0d7b4-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0d7b4-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0d7b4-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0d7b4-110">Qubit registr, který se má změřit</span><span class="sxs-lookup"><span data-stu-id="0d7b4-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="0d7b4-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="0d7b4-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="0d7b4-112">Výsledek měření daného Pauli operátoru v `target` registru</span><span class="sxs-lookup"><span data-stu-id="0d7b4-112">The result of measuring the given Pauli operator on the `target` register.</span></span>