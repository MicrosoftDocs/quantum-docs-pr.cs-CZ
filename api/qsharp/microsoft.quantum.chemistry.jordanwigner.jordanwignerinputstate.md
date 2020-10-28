---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: Uživatelem definovaný typ JordanWignerInputState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 171a2999ab8c73925d4624c565bfd41a4e73c99d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698440"
---
# <a name="jordanwignerinputstate-user-defined-type"></a><span data-ttu-id="36eaa-102">Uživatelem definovaný typ JordanWignerInputState</span><span class="sxs-lookup"><span data-stu-id="36eaa-102">JordanWignerInputState user defined type</span></span>

<span data-ttu-id="36eaa-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="36eaa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="36eaa-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36eaa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36eaa-105">Formát dat předaných z C# na Q # představující přípravu počátečního stavu. význam zobrazených dat závisí na algoritmu, který ho přijímá.</span><span class="sxs-lookup"><span data-stu-id="36eaa-105">Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

