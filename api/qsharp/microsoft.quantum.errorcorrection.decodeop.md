---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: Uživatelem definovaný typ DecodeOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 2b3d4558f6528c2e0f597398d12fc9331ab381b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827372"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="54573-102">Uživatelem definovaný typ DecodeOp</span><span class="sxs-lookup"><span data-stu-id="54573-102">DecodeOp user defined type</span></span>

<span data-ttu-id="54573-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="54573-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="54573-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="54573-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="54573-105">Představuje operaci, která dekóduje kódovaný registr do fyzického registru a pomocné qubitsy použité k zaznamenání Syndrome.</span><span class="sxs-lookup"><span data-stu-id="54573-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="54573-106">Argument pro DecodeOp je stejný jako návrat z EncodeOp a naopak.</span><span class="sxs-lookup"><span data-stu-id="54573-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

