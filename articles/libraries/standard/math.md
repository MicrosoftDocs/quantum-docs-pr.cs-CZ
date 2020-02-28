---
title: 'Matematické v knihovně Q # Standard'
description: 'Přečtěte si o klasických matematických funkcích ve standardních knihovnách Q #, které se používají s vestavěnými datovými typy.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906147"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="56cc2-103">Klasické matematické funkce</span><span class="sxs-lookup"><span data-stu-id="56cc2-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="56cc2-104">Tyto funkce jsou primárně používány pro práci s vestavěnými datovými typy Q # `Int`, `Double`a `Range`.</span><span class="sxs-lookup"><span data-stu-id="56cc2-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="56cc2-105">Operace <xref:microsoft.quantum.intrinsic.random> má `(Double[] => Int)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="56cc2-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="56cc2-106">Přebírá pole dvojitých hodnot jako vstup a vrací náhodně vybraný index do pole jako `Int`.</span><span class="sxs-lookup"><span data-stu-id="56cc2-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="56cc2-107">Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu.</span><span class="sxs-lookup"><span data-stu-id="56cc2-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="56cc2-108">prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí.</span><span class="sxs-lookup"><span data-stu-id="56cc2-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="56cc2-109">Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.</span><span class="sxs-lookup"><span data-stu-id="56cc2-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
