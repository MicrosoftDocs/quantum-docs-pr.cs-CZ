---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Uživatelem definovaný typ SyndromeMeasOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200250"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="2d6d5-102">Uživatelem definovaný typ SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="2d6d5-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="2d6d5-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="2d6d5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="2d6d5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d6d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d6d5-105">Představuje operaci, která slouží k měření Syndrome bloku kódu chyby.</span><span class="sxs-lookup"><span data-stu-id="2d6d5-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="2d6d5-106">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2d6d5-106">Remarks</span></span>

<span data-ttu-id="2d6d5-107">Signatura `(LogicalRegister => Syndrome)` představuje operaci, která funguje společně na qubits v `LogicalRegister` a některých pomocných qubits následovaných měřením pomocných qubitsů k extrakci `Syndrome` hodnoty představující `Result[]` Tato měření.</span><span class="sxs-lookup"><span data-stu-id="2d6d5-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d6d5-108">Viz také</span><span class="sxs-lookup"><span data-stu-id="2d6d5-108">See Also</span></span>

- [<span data-ttu-id="2d6d5-109">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="2d6d5-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="2d6d5-110">Microsoft. ErrorCorrection. Syndrome</span><span class="sxs-lookup"><span data-stu-id="2d6d5-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)