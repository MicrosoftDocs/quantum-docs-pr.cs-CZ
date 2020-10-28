---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operace MResetX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709081"
---
# <a name="mresetx-operation"></a><span data-ttu-id="36cc4-102">Operace MResetX</span><span class="sxs-lookup"><span data-stu-id="36cc4-102">MResetX operation</span></span>

<span data-ttu-id="36cc4-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="36cc4-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="36cc4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36cc4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36cc4-105">Měří jeden qubit v ose X a obnoví ho do pevného počátečního stavu po měření.</span><span class="sxs-lookup"><span data-stu-id="36cc4-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="36cc4-106">Popis</span><span class="sxs-lookup"><span data-stu-id="36cc4-106">Description</span></span>

<span data-ttu-id="36cc4-107">Provede qubit měření v $X $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.</span><span class="sxs-lookup"><span data-stu-id="36cc4-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="36cc4-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="36cc4-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="36cc4-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="36cc4-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="36cc4-110">Jedna qubit, která se má změřit</span><span class="sxs-lookup"><span data-stu-id="36cc4-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="36cc4-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="36cc4-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="36cc4-112">Výsledek měření `target` v Pauli $X $ základ.</span><span class="sxs-lookup"><span data-stu-id="36cc4-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>