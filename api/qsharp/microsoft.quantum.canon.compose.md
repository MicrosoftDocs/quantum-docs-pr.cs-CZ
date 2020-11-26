---
uid: Microsoft.Quantum.Canon.Compose
title: Funkce pro vytváření
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216757"
---
# <a name="compose-function"></a><span data-ttu-id="b066e-102">Funkce pro vytváření</span><span class="sxs-lookup"><span data-stu-id="b066e-102">Compose function</span></span>

<span data-ttu-id="b066e-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b066e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b066e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b066e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b066e-105">Vrátí kompozici dvou funkcí.</span><span class="sxs-lookup"><span data-stu-id="b066e-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="b066e-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b066e-106">Description</span></span>

<span data-ttu-id="b066e-107">Zadané dvě funkce $f $ a $g $, vrátí novou funkci reprezentující $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="b066e-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="b066e-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="b066e-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="b066e-109">vnější: U-> V</span><span class="sxs-lookup"><span data-stu-id="b066e-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="b066e-110">Druhá funkce, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="b066e-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="b066e-111">vnitřní: t-> ' U</span><span class="sxs-lookup"><span data-stu-id="b066e-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="b066e-112">První funkce, která se má použít</span><span class="sxs-lookup"><span data-stu-id="b066e-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="b066e-113">Výstup: t-> ' V</span><span class="sxs-lookup"><span data-stu-id="b066e-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="b066e-114">Nová funkce $h $, což pro všechny vstupy $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="b066e-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b066e-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b066e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b066e-116">'S</span><span class="sxs-lookup"><span data-stu-id="b066e-116">'T</span></span>

<span data-ttu-id="b066e-117">Vstupní typ první funkce, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="b066e-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="b066e-118">U</span><span class="sxs-lookup"><span data-stu-id="b066e-118">'U</span></span>

<span data-ttu-id="b066e-119">Typ výstupu první funkce, která má být použita, a vstupní typ druhé funkce, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="b066e-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="b066e-120">V</span><span class="sxs-lookup"><span data-stu-id="b066e-120">'V</span></span>

<span data-ttu-id="b066e-121">Typ výstupu druhé funkce, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="b066e-121">The output type of the second function to be applied.</span></span>