---
uid: Microsoft.Quantum.Math.PlusA
title: Funkce plus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842700"
---
# <a name="plusa-function"></a><span data-ttu-id="75198-102">Funkce plus</span><span class="sxs-lookup"><span data-stu-id="75198-102">PlusA function</span></span>

<span data-ttu-id="75198-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="75198-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="75198-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75198-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75198-105">Vrátí součet (zřetězení) dvou vstupů.</span><span class="sxs-lookup"><span data-stu-id="75198-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="75198-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="75198-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="75198-107">a: ' element []</span><span class="sxs-lookup"><span data-stu-id="75198-107">a : 'Element[]</span></span>

<span data-ttu-id="75198-108">První vstupní $a $, která se má sečíst</span><span class="sxs-lookup"><span data-stu-id="75198-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="75198-109">b: ' element []</span><span class="sxs-lookup"><span data-stu-id="75198-109">b : 'Element[]</span></span>

<span data-ttu-id="75198-110">Druhý vstup $b $ se má sečíst.</span><span class="sxs-lookup"><span data-stu-id="75198-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="75198-111">Výstup: ' element []</span><span class="sxs-lookup"><span data-stu-id="75198-111">Output : 'Element[]</span></span>

<span data-ttu-id="75198-112">Suma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="75198-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="75198-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="75198-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="75198-114">Element</span><span class="sxs-lookup"><span data-stu-id="75198-114">'Element</span></span>

<span data-ttu-id="75198-115">Typ každého prvku v každé ze dvou vstupních polí.</span><span class="sxs-lookup"><span data-stu-id="75198-115">The type of each element in each of the two input arrays.</span></span>