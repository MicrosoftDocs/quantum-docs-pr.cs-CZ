---
uid: Microsoft.Quantum.Simulation.Unitary
title: Typ jednotně definovaného uživatele
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: c34d84fb5f319c285356b284bd1f1c18ec64ef46
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192141"
---
# <a name="unitary-user-defined-type"></a><span data-ttu-id="02cc8-102">Typ jednotně definovaného uživatele</span><span class="sxs-lookup"><span data-stu-id="02cc8-102">Unitary user defined type</span></span>

<span data-ttu-id="02cc8-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="02cc8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="02cc8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02cc8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02cc8-105">Představuje vývoj pod operátorem s jednou jednotkou.</span><span class="sxs-lookup"><span data-stu-id="02cc8-105">Represents evolution under a unitary operator.</span></span>

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

