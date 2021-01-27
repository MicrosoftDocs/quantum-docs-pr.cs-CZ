---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operace MeasureAllZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854676"
---
# <a name="measureallz-operation"></a><span data-ttu-id="c8596-102">Operace MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="c8596-102">MeasureAllZ operation</span></span>

<span data-ttu-id="c8596-103">Obor názvů: [Microsoft. proměření](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="c8596-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="c8596-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8596-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8596-105">Společně měří Registry qubits v Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="c8596-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="c8596-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c8596-106">Description</span></span>

<span data-ttu-id="c8596-107">Měří Registry qubits v $Z \otimes Z \otimes \cdots \otimes Z $, které představují paritu celého registru.</span><span class="sxs-lookup"><span data-stu-id="c8596-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="c8596-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="c8596-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="c8596-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c8596-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c8596-110">Registr, který se má měřit</span><span class="sxs-lookup"><span data-stu-id="c8596-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c8596-111">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="c8596-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="c8596-112">Výsledek měření $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="c8596-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>