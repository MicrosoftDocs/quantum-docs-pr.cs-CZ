---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Uživatelem definovaný typ SyndromeMeasOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850056"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="22c58-102">Uživatelem definovaný typ SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="22c58-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="22c58-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="22c58-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="22c58-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22c58-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22c58-105">Představuje operaci, která slouží k měření Syndrome bloku kódu chyby.</span><span class="sxs-lookup"><span data-stu-id="22c58-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="22c58-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="22c58-106">Example</span></span>

<span data-ttu-id="22c58-107">Syndromes míry pro překlápění kódu $S = \langle ZZI, IZZ \rangle $ použití pomocné qubits v případě, že je odolný proti chybám:</span><span class="sxs-lookup"><span data-stu-id="22c58-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="22c58-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="22c58-108">Remarks</span></span>

<span data-ttu-id="22c58-109">Signatura `(LogicalRegister => Syndrome)` představuje operaci, která funguje společně na qubits v `LogicalRegister` a některých pomocných qubits následovaných měřením pomocných qubitsů k extrakci `Syndrome` hodnoty představující `Result[]` Tato měření.</span><span class="sxs-lookup"><span data-stu-id="22c58-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="22c58-110">Viz také</span><span class="sxs-lookup"><span data-stu-id="22c58-110">See Also</span></span>

- [<span data-ttu-id="22c58-111">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="22c58-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="22c58-112">Microsoft. ErrorCorrection. Syndrome</span><span class="sxs-lookup"><span data-stu-id="22c58-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)