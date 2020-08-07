---
title: Matematické Q# standardní knihovny
description: Přečtěte si o klasických matematických funkcích ve Q# standardních knihovnách, které se používají s vestavěnými datovými typy.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868419"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="1197f-103">Klasické matematické funkce</span><span class="sxs-lookup"><span data-stu-id="1197f-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="1197f-104">Tyto funkce jsou primárně používány pro práci s Q# vestavěnými datovými typy `Int` , `Double` a `Range` .</span><span class="sxs-lookup"><span data-stu-id="1197f-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="1197f-105"><xref:microsoft.quantum.intrinsic.random>Operace má signaturu `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="1197f-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="1197f-106">Přebírá pole dvojitých hodnot jako vstup a vrátí náhodně vybraný index do pole jako `Int` .</span><span class="sxs-lookup"><span data-stu-id="1197f-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="1197f-107">Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu.</span><span class="sxs-lookup"><span data-stu-id="1197f-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="1197f-108">prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí.</span><span class="sxs-lookup"><span data-stu-id="1197f-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="1197f-109">Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.</span><span class="sxs-lookup"><span data-stu-id="1197f-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
