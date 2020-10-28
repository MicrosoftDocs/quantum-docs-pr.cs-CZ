---
uid: Microsoft.Quantum.ErrorCorrection.CSS
title: Uživatelsky definovaný typ CSS
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: CSS
qsharp.summary: Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.
ms.openlocfilehash: c5227c771ec2c7c81d05a28681745af641eebeaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698013"
---
# <a name="css-user-defined-type"></a><span data-ttu-id="09c6f-102">Uživatelsky definovaný typ CSS</span><span class="sxs-lookup"><span data-stu-id="09c6f-102">CSS user defined type</span></span>

<span data-ttu-id="09c6f-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="09c6f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="09c6f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09c6f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09c6f-105">Představuje kód Calderbank – Shor – Steane (CSS) podle definice kodéru, dekodéru a jeho postupů Syndrome měření pro `X` chyby a v `Z` uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="09c6f-105">Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.</span></span>

```qsharp

newtype CSS = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

