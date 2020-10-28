---
uid: Microsoft.Quantum.Canon.Fst
title: FST – – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704177"
---
# <a name="fst-function"></a><span data-ttu-id="e1e44-102">FST – – funkce</span><span class="sxs-lookup"><span data-stu-id="e1e44-102">Fst function</span></span>

<span data-ttu-id="e1e44-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e1e44-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e1e44-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1e44-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1e44-105">V případě páru vrátí jeho první prvek.</span><span class="sxs-lookup"><span data-stu-id="e1e44-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="e1e44-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e1e44-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="e1e44-107">dvojice: (t, ' U)</span><span class="sxs-lookup"><span data-stu-id="e1e44-107">pair : ('T,'U)</span></span>

<span data-ttu-id="e1e44-108">Řazená kolekce členů se dvěma prvky.</span><span class="sxs-lookup"><span data-stu-id="e1e44-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="e1e44-109">Výstup: 'T</span><span class="sxs-lookup"><span data-stu-id="e1e44-109">Output : 'T</span></span>

<span data-ttu-id="e1e44-110">První prvek `pair` .</span><span class="sxs-lookup"><span data-stu-id="e1e44-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e1e44-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e1e44-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1e44-112">'S</span><span class="sxs-lookup"><span data-stu-id="e1e44-112">'T</span></span>

<span data-ttu-id="e1e44-113">Typ prvního člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="e1e44-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="e1e44-114">U</span><span class="sxs-lookup"><span data-stu-id="e1e44-114">'U</span></span>

<span data-ttu-id="e1e44-115">Typ druhého člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="e1e44-115">The type of the pair's second member.</span></span>