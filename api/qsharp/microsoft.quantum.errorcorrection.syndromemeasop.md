---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Uživatelem definovaný typ SyndromeMeasOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697908"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="4bb40-102">Uživatelem definovaný typ SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="4bb40-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="4bb40-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4bb40-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4bb40-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4bb40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4bb40-105">Představuje operaci, která slouží k měření Syndrome bloku kódu chyby.</span><span class="sxs-lookup"><span data-stu-id="4bb40-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="4bb40-106">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4bb40-106">Remarks</span></span>

<span data-ttu-id="4bb40-107">Signatura `(LogicalRegister => Syndrome)` představuje operaci, která funguje společně na qubits v `LogicalRegister` a některých pomocných qubits následovaných měřením pomocných qubitsů k extrakci `Syndrome` hodnoty představující `Result[]` Tato měření.</span><span class="sxs-lookup"><span data-stu-id="4bb40-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="4bb40-108">Viz také</span><span class="sxs-lookup"><span data-stu-id="4bb40-108">See Also</span></span>

- [<span data-ttu-id="4bb40-109">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="4bb40-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="4bb40-110">Microsoft. ErrorCorrection. Syndrome</span><span class="sxs-lookup"><span data-stu-id="4bb40-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)