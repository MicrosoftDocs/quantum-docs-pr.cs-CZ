---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 2d0b50bd2467fc01caacbbcb22f98c59a2d13922
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201219"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="125d6-102">BitFlipCode – funkce</span><span class="sxs-lookup"><span data-stu-id="125d6-102">BitFlipCode function</span></span>

<span data-ttu-id="125d6-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="125d6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="125d6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="125d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="125d6-105">Vrátí hodnotu QECC představující ⟦ 3, 1, 1 ⟧ bit převráceného kodéru a dekodéru pomocí místního měření Syndrome.</span><span class="sxs-lookup"><span data-stu-id="125d6-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="125d6-106">Výstup: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="125d6-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="125d6-107">Vrací implementaci kódu opravy chyb pro každé z nich zadáním `QECC` typu.</span><span class="sxs-lookup"><span data-stu-id="125d6-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>