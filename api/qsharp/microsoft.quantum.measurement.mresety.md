---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operace MResetY
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227025"
---
# <a name="mresety-operation"></a><span data-ttu-id="20691-102">Operace MResetY</span><span class="sxs-lookup"><span data-stu-id="20691-102">MResetY operation</span></span>

<span data-ttu-id="20691-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="20691-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="20691-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="20691-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="20691-105">Měří jeden qubit v ose Y a obnoví ho do pevného počátečního stavu po měření.</span><span class="sxs-lookup"><span data-stu-id="20691-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="20691-106">Popis</span><span class="sxs-lookup"><span data-stu-id="20691-106">Description</span></span>

<span data-ttu-id="20691-107">Provede qubit měření v $Y $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.</span><span class="sxs-lookup"><span data-stu-id="20691-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="20691-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="20691-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="20691-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="20691-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="20691-110">Jedna qubit, která se má změřit</span><span class="sxs-lookup"><span data-stu-id="20691-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="20691-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="20691-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="20691-112">Výsledek měření `target` v Pauli $Y $ základ.</span><span class="sxs-lookup"><span data-stu-id="20691-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>