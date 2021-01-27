---
title: Matematické Q# standardní knihovny
description: Přečtěte si o klasických matematických funkcích ve Q# standardních knihovnách, které se používají s vestavěnými datovými typy.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2e2656f42213c8ae9e984f63f3ebf4058520532
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853994"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="583c2-103">Klasické matematické funkce</span><span class="sxs-lookup"><span data-stu-id="583c2-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="583c2-104">Tyto funkce jsou primárně používány pro práci s Q# vestavěnými datovými typy `Int` , `Double` a `Range` .</span><span class="sxs-lookup"><span data-stu-id="583c2-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="583c2-105"><xref:Microsoft.Quantum.Intrinsic.Random>Operace má signaturu `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="583c2-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="583c2-106">Přebírá pole dvojitých hodnot jako vstup a vrátí náhodně vybraný index do pole jako `Int` .</span><span class="sxs-lookup"><span data-stu-id="583c2-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="583c2-107">Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu.</span><span class="sxs-lookup"><span data-stu-id="583c2-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="583c2-108">prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí.</span><span class="sxs-lookup"><span data-stu-id="583c2-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="583c2-109">Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.</span><span class="sxs-lookup"><span data-stu-id="583c2-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
