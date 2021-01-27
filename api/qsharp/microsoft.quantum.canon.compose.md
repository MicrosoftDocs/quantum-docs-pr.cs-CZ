---
uid: Microsoft.Quantum.Canon.Compose
title: Funkce pro vytváření
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840906"
---
# <a name="compose-function"></a><span data-ttu-id="1ce47-102">Funkce pro vytváření</span><span class="sxs-lookup"><span data-stu-id="1ce47-102">Compose function</span></span>

<span data-ttu-id="1ce47-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1ce47-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1ce47-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ce47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1ce47-105">Vrátí kompozici dvou funkcí.</span><span class="sxs-lookup"><span data-stu-id="1ce47-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="1ce47-106">Popis</span><span class="sxs-lookup"><span data-stu-id="1ce47-106">Description</span></span>

<span data-ttu-id="1ce47-107">Zadané dvě funkce $f $ a $g $, vrátí novou funkci reprezentující $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="1ce47-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="1ce47-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="1ce47-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="1ce47-109">vnější: U-> V</span><span class="sxs-lookup"><span data-stu-id="1ce47-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="1ce47-110">Druhá funkce, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="1ce47-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="1ce47-111">vnitřní: t-> ' U</span><span class="sxs-lookup"><span data-stu-id="1ce47-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="1ce47-112">První funkce, která se má použít</span><span class="sxs-lookup"><span data-stu-id="1ce47-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="1ce47-113">Výstup: t-> ' V</span><span class="sxs-lookup"><span data-stu-id="1ce47-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="1ce47-114">Nová funkce $h $, což pro všechny vstupy $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="1ce47-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1ce47-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1ce47-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1ce47-116">'S</span><span class="sxs-lookup"><span data-stu-id="1ce47-116">'T</span></span>

<span data-ttu-id="1ce47-117">Vstupní typ první funkce, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="1ce47-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="1ce47-118">U</span><span class="sxs-lookup"><span data-stu-id="1ce47-118">'U</span></span>

<span data-ttu-id="1ce47-119">Typ výstupu první funkce, která má být použita, a vstupní typ druhé funkce, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="1ce47-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="1ce47-120">V</span><span class="sxs-lookup"><span data-stu-id="1ce47-120">'V</span></span>

<span data-ttu-id="1ce47-121">Typ výstupu druhé funkce, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="1ce47-121">The output type of the second function to be applied.</span></span>