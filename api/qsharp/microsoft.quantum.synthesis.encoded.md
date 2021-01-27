---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Encoded – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855487"
---
# <a name="encoded-function"></a><span data-ttu-id="a2c31-102">Encoded – funkce</span><span class="sxs-lookup"><span data-stu-id="a2c31-102">Encoded function</span></span>

<span data-ttu-id="a2c31-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a2c31-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a2c31-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2c31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2c31-105">Kódovat tabulku pravdy v {1,-1} kódování</span><span class="sxs-lookup"><span data-stu-id="a2c31-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="a2c31-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a2c31-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="a2c31-107">Tabulka: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a2c31-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a2c31-108">Tabulka pravdy jako pole hodnot hodnoty pravdy</span><span class="sxs-lookup"><span data-stu-id="a2c31-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="a2c31-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a2c31-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a2c31-110">Tabulka pravdy jako pole {1,-1} celých čísel</span><span class="sxs-lookup"><span data-stu-id="a2c31-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="a2c31-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="a2c31-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```