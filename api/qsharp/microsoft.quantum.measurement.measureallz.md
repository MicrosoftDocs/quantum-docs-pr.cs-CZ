---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operace MeasureAllZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227076"
---
# <a name="measureallz-operation"></a><span data-ttu-id="4e501-102">Operace MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="4e501-102">MeasureAllZ operation</span></span>

<span data-ttu-id="4e501-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="4e501-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="4e501-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e501-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e501-105">Společně měří Registry qubits v Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="4e501-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="4e501-106">Popis</span><span class="sxs-lookup"><span data-stu-id="4e501-106">Description</span></span>

<span data-ttu-id="4e501-107">Měří Registry qubits v $Z \otimes Z \otimes \cdots \otimes Z $, které představují paritu celého registru.</span><span class="sxs-lookup"><span data-stu-id="4e501-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="4e501-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="4e501-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="4e501-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4e501-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4e501-110">Registr, který se má měřit</span><span class="sxs-lookup"><span data-stu-id="4e501-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="4e501-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="4e501-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="4e501-112">Výsledek měření $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="4e501-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>