---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operace MResetX
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853764"
---
# <a name="mresetx-operation"></a><span data-ttu-id="1b74c-102">Operace MResetX</span><span class="sxs-lookup"><span data-stu-id="1b74c-102">MResetX operation</span></span>

<span data-ttu-id="1b74c-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="1b74c-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="1b74c-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1b74c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1b74c-105">Měří jeden qubit v ose X a obnoví ho do pevného počátečního stavu po měření.</span><span class="sxs-lookup"><span data-stu-id="1b74c-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="1b74c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="1b74c-106">Description</span></span>

<span data-ttu-id="1b74c-107">Provede qubit měření v $X $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.</span><span class="sxs-lookup"><span data-stu-id="1b74c-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="1b74c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="1b74c-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="1b74c-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1b74c-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1b74c-110">Jedna qubit, která se má změřit</span><span class="sxs-lookup"><span data-stu-id="1b74c-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="1b74c-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="1b74c-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="1b74c-112">Výsledek měření `target` v Pauli $X $ základ.</span><span class="sxs-lookup"><span data-stu-id="1b74c-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>