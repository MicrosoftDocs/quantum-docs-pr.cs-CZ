---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Encoded – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203174"
---
# <a name="encoded-function"></a><span data-ttu-id="73ea1-102">Encoded – funkce</span><span class="sxs-lookup"><span data-stu-id="73ea1-102">Encoded function</span></span>

<span data-ttu-id="73ea1-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="73ea1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="73ea1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73ea1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73ea1-105">Kódovat tabulku pravdy v {1,-1} kódování</span><span class="sxs-lookup"><span data-stu-id="73ea1-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="73ea1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="73ea1-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="73ea1-107">Tabulka: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="73ea1-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="73ea1-108">Tabulka pravdy jako pole hodnot hodnoty pravdy</span><span class="sxs-lookup"><span data-stu-id="73ea1-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="73ea1-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="73ea1-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="73ea1-110">Tabulka pravdy jako pole {1,-1} celých čísel</span><span class="sxs-lookup"><span data-stu-id="73ea1-110">Truth table as array of {1,-1} integers</span></span>