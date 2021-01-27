---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: Uživatelem definovaný typ EncodeOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: c9959f1afbd44df974c06b79f73eccd090b17985
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826181"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="eeaee-102">Uživatelem definovaný typ EncodeOp</span><span class="sxs-lookup"><span data-stu-id="eeaee-102">EncodeOp user defined type</span></span>

<span data-ttu-id="eeaee-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="eeaee-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="eeaee-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eeaee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eeaee-105">Představuje operaci, která kóduje fyzický registr do logického registru pomocí poskytnutých pomocných qubits.</span><span class="sxs-lookup"><span data-stu-id="eeaee-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="eeaee-106">První argument se považuje za fyzický registr, který se zakóduje, zatímco druhý argument je pomocným registračním registrem, který se bude používat.</span><span class="sxs-lookup"><span data-stu-id="eeaee-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

