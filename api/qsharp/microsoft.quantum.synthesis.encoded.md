---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Encoded – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709166"
---
# <a name="encoded-function"></a><span data-ttu-id="d9ed4-102">Encoded – funkce</span><span class="sxs-lookup"><span data-stu-id="d9ed4-102">Encoded function</span></span>

<span data-ttu-id="d9ed4-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d9ed4-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d9ed4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9ed4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9ed4-105">Kódovat tabulku pravdy v {1,-1} kódování</span><span class="sxs-lookup"><span data-stu-id="d9ed4-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="d9ed4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d9ed4-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="d9ed4-107">Tabulka: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d9ed4-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d9ed4-108">Tabulka pravdy jako pole hodnot hodnoty pravdy</span><span class="sxs-lookup"><span data-stu-id="d9ed4-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="d9ed4-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d9ed4-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d9ed4-110">Tabulka pravdy jako pole {1,-1} celých čísel</span><span class="sxs-lookup"><span data-stu-id="d9ed4-110">Truth table as array of {1,-1} integers</span></span>