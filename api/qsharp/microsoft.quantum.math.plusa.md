---
uid: Microsoft.Quantum.Math.PlusA
title: Funkce plus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194827"
---
# <a name="plusa-function"></a><span data-ttu-id="988fc-102">Funkce plus</span><span class="sxs-lookup"><span data-stu-id="988fc-102">PlusA function</span></span>

<span data-ttu-id="988fc-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="988fc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="988fc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="988fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="988fc-105">Vrátí součet (zřetězení) dvou vstupů.</span><span class="sxs-lookup"><span data-stu-id="988fc-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="988fc-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="988fc-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="988fc-107">a: ' element []</span><span class="sxs-lookup"><span data-stu-id="988fc-107">a : 'Element[]</span></span>

<span data-ttu-id="988fc-108">První vstupní $a $, která se má sečíst</span><span class="sxs-lookup"><span data-stu-id="988fc-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="988fc-109">b: ' element []</span><span class="sxs-lookup"><span data-stu-id="988fc-109">b : 'Element[]</span></span>

<span data-ttu-id="988fc-110">Druhý vstup $b $ se má sečíst.</span><span class="sxs-lookup"><span data-stu-id="988fc-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="988fc-111">Výstup: ' element []</span><span class="sxs-lookup"><span data-stu-id="988fc-111">Output : 'Element[]</span></span>

<span data-ttu-id="988fc-112">Suma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="988fc-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="988fc-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="988fc-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="988fc-114">Element</span><span class="sxs-lookup"><span data-stu-id="988fc-114">'Element</span></span>

<span data-ttu-id="988fc-115">Typ každého prvku v každé ze dvou vstupních polí.</span><span class="sxs-lookup"><span data-stu-id="988fc-115">The type of each element in each of the two input arrays.</span></span>