---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operace MResetY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854641"
---
# <a name="mresety-operation"></a><span data-ttu-id="d30e2-102">Operace MResetY</span><span class="sxs-lookup"><span data-stu-id="d30e2-102">MResetY operation</span></span>

<span data-ttu-id="d30e2-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="d30e2-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="d30e2-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d30e2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d30e2-105">Měří jeden qubit v ose Y a obnoví ho do pevného počátečního stavu po měření.</span><span class="sxs-lookup"><span data-stu-id="d30e2-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="d30e2-106">Popis</span><span class="sxs-lookup"><span data-stu-id="d30e2-106">Description</span></span>

<span data-ttu-id="d30e2-107">Provede qubit měření v $Y $-základ a zajistí, že qubit se vrátí do $ \ket {0} $ za měřením.</span><span class="sxs-lookup"><span data-stu-id="d30e2-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="d30e2-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="d30e2-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="d30e2-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d30e2-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d30e2-110">Jedna qubit, která se má změřit</span><span class="sxs-lookup"><span data-stu-id="d30e2-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="d30e2-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="d30e2-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="d30e2-112">Výsledek měření `target` v Pauli $Y $ základ.</span><span class="sxs-lookup"><span data-stu-id="d30e2-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>