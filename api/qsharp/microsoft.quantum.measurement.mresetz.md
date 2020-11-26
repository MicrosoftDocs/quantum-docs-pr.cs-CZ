---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operace MResetZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194130"
---
# <a name="mresetz-operation"></a><span data-ttu-id="16696-102">Operace MResetZ</span><span class="sxs-lookup"><span data-stu-id="16696-102">MResetZ operation</span></span>

<span data-ttu-id="16696-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="16696-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="16696-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="16696-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="16696-105">Měří jeden qubit v rámci a obnoví ho do pevného počátečního stavu po měření.</span><span class="sxs-lookup"><span data-stu-id="16696-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="16696-106">Popis</span><span class="sxs-lookup"><span data-stu-id="16696-106">Description</span></span>

<span data-ttu-id="16696-107">Provede qubit měření v $Z $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.</span><span class="sxs-lookup"><span data-stu-id="16696-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="16696-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="16696-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="16696-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="16696-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="16696-110">Jedna qubit, která se má změřit</span><span class="sxs-lookup"><span data-stu-id="16696-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="16696-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="16696-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="16696-112">Výsledek měření `target` v Pauli $Z $ základ.</span><span class="sxs-lookup"><span data-stu-id="16696-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>