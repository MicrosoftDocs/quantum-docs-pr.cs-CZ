---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: Uživatelem definovaný typ DecodeOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: f1fc2851b7ed8b12cf8a47fabe794235a3083d31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200998"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="907fd-102">Uživatelem definovaný typ DecodeOp</span><span class="sxs-lookup"><span data-stu-id="907fd-102">DecodeOp user defined type</span></span>

<span data-ttu-id="907fd-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="907fd-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="907fd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="907fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="907fd-105">Představuje operaci, která dekóduje kódovaný registr do fyzického registru a pomocné qubitsy použité k zaznamenání Syndrome.</span><span class="sxs-lookup"><span data-stu-id="907fd-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="907fd-106">Argument pro DecodeOp je stejný jako návrat z EncodeOp a naopak.</span><span class="sxs-lookup"><span data-stu-id="907fd-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

