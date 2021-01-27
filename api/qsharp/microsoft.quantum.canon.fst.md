---
uid: Microsoft.Quantum.Canon.Fst
title: FST – – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840521"
---
# <a name="fst-function"></a><span data-ttu-id="c9e1f-102">FST – – funkce</span><span class="sxs-lookup"><span data-stu-id="c9e1f-102">Fst function</span></span>

<span data-ttu-id="c9e1f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9e1f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9e1f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9e1f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9e1f-105">V případě páru vrátí jeho první prvek.</span><span class="sxs-lookup"><span data-stu-id="c9e1f-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="c9e1f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c9e1f-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="c9e1f-107">dvojice: (t, ' U)</span><span class="sxs-lookup"><span data-stu-id="c9e1f-107">pair : ('T,'U)</span></span>

<span data-ttu-id="c9e1f-108">Řazená kolekce členů se dvěma prvky.</span><span class="sxs-lookup"><span data-stu-id="c9e1f-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="c9e1f-109">Výstup: 'T</span><span class="sxs-lookup"><span data-stu-id="c9e1f-109">Output : 'T</span></span>

<span data-ttu-id="c9e1f-110">První prvek `pair` .</span><span class="sxs-lookup"><span data-stu-id="c9e1f-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c9e1f-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c9e1f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9e1f-112">'S</span><span class="sxs-lookup"><span data-stu-id="c9e1f-112">'T</span></span>

<span data-ttu-id="c9e1f-113">Typ prvního člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="c9e1f-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="c9e1f-114">U</span><span class="sxs-lookup"><span data-stu-id="c9e1f-114">'U</span></span>

<span data-ttu-id="c9e1f-115">Typ druhého člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="c9e1f-115">The type of the pair's second member.</span></span>