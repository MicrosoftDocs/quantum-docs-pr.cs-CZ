---
uid: Microsoft.Quantum.Math.PlusA
title: Funkce plus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697189"
---
# <a name="plusa-function"></a><span data-ttu-id="dbb87-102">Funkce plus</span><span class="sxs-lookup"><span data-stu-id="dbb87-102">PlusA function</span></span>

<span data-ttu-id="dbb87-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="dbb87-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="dbb87-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbb87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbb87-105">Vrátí součet (zřetězení) dvou vstupů.</span><span class="sxs-lookup"><span data-stu-id="dbb87-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="dbb87-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="dbb87-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="dbb87-107">a: ' element []</span><span class="sxs-lookup"><span data-stu-id="dbb87-107">a : 'Element[]</span></span>

<span data-ttu-id="dbb87-108">První vstupní $a $, která se má sečíst</span><span class="sxs-lookup"><span data-stu-id="dbb87-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="dbb87-109">b: ' element []</span><span class="sxs-lookup"><span data-stu-id="dbb87-109">b : 'Element[]</span></span>

<span data-ttu-id="dbb87-110">Druhý vstup $b $ se má sečíst.</span><span class="sxs-lookup"><span data-stu-id="dbb87-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="dbb87-111">Výstup: ' element []</span><span class="sxs-lookup"><span data-stu-id="dbb87-111">Output : 'Element[]</span></span>

<span data-ttu-id="dbb87-112">Suma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="dbb87-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dbb87-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="dbb87-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="dbb87-114">Element</span><span class="sxs-lookup"><span data-stu-id="dbb87-114">'Element</span></span>

<span data-ttu-id="dbb87-115">Typ každého prvku v každé ze dvou vstupních polí.</span><span class="sxs-lookup"><span data-stu-id="dbb87-115">The type of each element in each of the two input arrays.</span></span>