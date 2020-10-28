---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: Uživatelem definovaný typ EncodeOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697973"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="4b54b-102">Uživatelem definovaný typ EncodeOp</span><span class="sxs-lookup"><span data-stu-id="4b54b-102">EncodeOp user defined type</span></span>

<span data-ttu-id="4b54b-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4b54b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4b54b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b54b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b54b-105">Představuje operaci, která kóduje fyzický registr do logického registru pomocí poskytnutých pomocných qubits.</span><span class="sxs-lookup"><span data-stu-id="4b54b-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="4b54b-106">První argument se považuje za fyzický registr, který se zakóduje, zatímco druhý argument je pomocným registračním registrem, který se bude používat.</span><span class="sxs-lookup"><span data-stu-id="4b54b-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

