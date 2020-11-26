---
uid: Microsoft.Quantum.Canon.Fst
title: FST – – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206931"
---
# <a name="fst-function"></a><span data-ttu-id="58537-102">FST – – funkce</span><span class="sxs-lookup"><span data-stu-id="58537-102">Fst function</span></span>

<span data-ttu-id="58537-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="58537-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="58537-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58537-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58537-105">V případě páru vrátí jeho první prvek.</span><span class="sxs-lookup"><span data-stu-id="58537-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="58537-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="58537-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="58537-107">dvojice: (t, ' U)</span><span class="sxs-lookup"><span data-stu-id="58537-107">pair : ('T,'U)</span></span>

<span data-ttu-id="58537-108">Řazená kolekce členů se dvěma prvky.</span><span class="sxs-lookup"><span data-stu-id="58537-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="58537-109">Výstup: 'T</span><span class="sxs-lookup"><span data-stu-id="58537-109">Output : 'T</span></span>

<span data-ttu-id="58537-110">První prvek `pair` .</span><span class="sxs-lookup"><span data-stu-id="58537-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="58537-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="58537-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="58537-112">'S</span><span class="sxs-lookup"><span data-stu-id="58537-112">'T</span></span>

<span data-ttu-id="58537-113">Typ prvního člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="58537-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="58537-114">U</span><span class="sxs-lookup"><span data-stu-id="58537-114">'U</span></span>

<span data-ttu-id="58537-115">Typ druhého člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="58537-115">The type of the pair's second member.</span></span>