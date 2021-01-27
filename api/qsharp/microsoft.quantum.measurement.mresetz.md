---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operace MResetZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853739"
---
# <a name="mresetz-operation"></a><span data-ttu-id="c1255-102">Operace MResetZ</span><span class="sxs-lookup"><span data-stu-id="c1255-102">MResetZ operation</span></span>

<span data-ttu-id="c1255-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="c1255-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="c1255-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c1255-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c1255-105">Měří jeden qubit v rámci a obnoví ho do pevného počátečního stavu po měření.</span><span class="sxs-lookup"><span data-stu-id="c1255-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="c1255-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c1255-106">Description</span></span>

<span data-ttu-id="c1255-107">Provede qubit měření v $Z $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.</span><span class="sxs-lookup"><span data-stu-id="c1255-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="c1255-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="c1255-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="c1255-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c1255-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c1255-110">Jedna qubit, která se má změřit</span><span class="sxs-lookup"><span data-stu-id="c1255-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c1255-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="c1255-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="c1255-112">Výsledek měření `target` v Pauli $Z $ základ.</span><span class="sxs-lookup"><span data-stu-id="c1255-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>