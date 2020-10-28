---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Operace MeasureWithScratch
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706745"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="6b890-102">Operace MeasureWithScratch</span><span class="sxs-lookup"><span data-stu-id="6b890-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="6b890-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="6b890-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="6b890-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6b890-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6b890-105">Měří zadaný Pauli operátor pomocí explicitního qubitho škrábance k provedení měření.</span><span class="sxs-lookup"><span data-stu-id="6b890-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="6b890-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6b890-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="6b890-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="6b890-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="6b890-108">Qubit Pauli operátor, který jste zadali jako pole operátorů s jedním qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="6b890-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6b890-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6b890-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6b890-110">Qubit registr, který se má změřit</span><span class="sxs-lookup"><span data-stu-id="6b890-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6b890-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="6b890-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6b890-112">Výsledek měření daného Pauli operátoru v `target` registru</span><span class="sxs-lookup"><span data-stu-id="6b890-112">The result of measuring the given Pauli operator on the `target` register.</span></span>