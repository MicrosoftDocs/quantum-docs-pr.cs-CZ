---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operace MResetZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697604"
---
# <a name="mresetz-operation"></a><span data-ttu-id="cd446-102">Operace MResetZ</span><span class="sxs-lookup"><span data-stu-id="cd446-102">MResetZ operation</span></span>

<span data-ttu-id="cd446-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="cd446-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="cd446-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd446-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd446-105">Měří jeden qubit v rámci a obnoví ho do pevného počátečního stavu po měření.</span><span class="sxs-lookup"><span data-stu-id="cd446-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="cd446-106">Popis</span><span class="sxs-lookup"><span data-stu-id="cd446-106">Description</span></span>

<span data-ttu-id="cd446-107">Provede qubit měření v $Z $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.</span><span class="sxs-lookup"><span data-stu-id="cd446-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="cd446-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="cd446-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="cd446-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cd446-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cd446-110">Jedna qubit, která se má změřit</span><span class="sxs-lookup"><span data-stu-id="cd446-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="cd446-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="cd446-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="cd446-112">Výsledek měření `target` v Pauli $Z $ základ.</span><span class="sxs-lookup"><span data-stu-id="cd446-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>