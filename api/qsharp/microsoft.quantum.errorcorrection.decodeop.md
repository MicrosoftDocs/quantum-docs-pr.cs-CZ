---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: Uživatelem definovaný typ DecodeOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 0733ec016e50a320b162b111c7d87c32140fdacb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697992"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="5debd-102">Uživatelem definovaný typ DecodeOp</span><span class="sxs-lookup"><span data-stu-id="5debd-102">DecodeOp user defined type</span></span>

<span data-ttu-id="5debd-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="5debd-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="5debd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5debd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5debd-105">Představuje operaci, která dekóduje kódovaný registr do fyzického registru a pomocné qubitsy použité k zaznamenání Syndrome.</span><span class="sxs-lookup"><span data-stu-id="5debd-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="5debd-106">Argument pro DecodeOp je stejný jako návrat z EncodeOp a naopak.</span><span class="sxs-lookup"><span data-stu-id="5debd-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

