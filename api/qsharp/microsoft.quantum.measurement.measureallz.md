---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operace MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697609"
---
# <a name="measureallz-operation"></a><span data-ttu-id="d3365-102">Operace MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="d3365-102">MeasureAllZ operation</span></span>

<span data-ttu-id="d3365-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="d3365-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="d3365-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3365-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3365-105">Společně měří Registry qubits v Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="d3365-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="d3365-106">Popis</span><span class="sxs-lookup"><span data-stu-id="d3365-106">Description</span></span>

<span data-ttu-id="d3365-107">Měří Registry qubits v $Z \otimes Z \otimes \cdots \otimes Z $, které představují paritu celého registru.</span><span class="sxs-lookup"><span data-stu-id="d3365-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="d3365-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="d3365-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="d3365-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d3365-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d3365-110">Registr, který se má měřit</span><span class="sxs-lookup"><span data-stu-id="d3365-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="d3365-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="d3365-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="d3365-112">Výsledek měření $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="d3365-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>