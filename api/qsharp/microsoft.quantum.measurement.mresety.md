---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operace MResetY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709082"
---
# <a name="mresety-operation"></a><span data-ttu-id="12d3a-102">Operace MResetY</span><span class="sxs-lookup"><span data-stu-id="12d3a-102">MResetY operation</span></span>

<span data-ttu-id="12d3a-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="12d3a-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="12d3a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12d3a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="12d3a-105">Měří jeden qubit v ose Y a obnoví ho do pevného počátečního stavu po měření.</span><span class="sxs-lookup"><span data-stu-id="12d3a-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="12d3a-106">Popis</span><span class="sxs-lookup"><span data-stu-id="12d3a-106">Description</span></span>

<span data-ttu-id="12d3a-107">Provede qubit měření v $Y $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.</span><span class="sxs-lookup"><span data-stu-id="12d3a-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="12d3a-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="12d3a-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="12d3a-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="12d3a-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="12d3a-110">Jedna qubit, která se má změřit</span><span class="sxs-lookup"><span data-stu-id="12d3a-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="12d3a-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="12d3a-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="12d3a-112">Výsledek měření `target` v Pauli $Y $ základ.</span><span class="sxs-lookup"><span data-stu-id="12d3a-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>