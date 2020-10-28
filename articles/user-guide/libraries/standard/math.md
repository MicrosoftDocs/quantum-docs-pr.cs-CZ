---
title: 'Matematické :::no-loc(Q#)::: standardní knihovny'
description: 'Přečtěte si o klasických matematických funkcích ve :::no-loc(Q#)::: standardních knihovnách, které se používají s vestavěnými datovými typy.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692060"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="0f67a-103">Klasické matematické funkce</span><span class="sxs-lookup"><span data-stu-id="0f67a-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="0f67a-104">Tyto funkce jsou primárně používány pro práci s :::no-loc(Q#)::: vestavěnými datovými typy `Int` , `Double` a `Range` .</span><span class="sxs-lookup"><span data-stu-id="0f67a-104">These functions are primarily used to work with the :::no-loc(Q#)::: built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="0f67a-105"><xref:Microsoft.Quantum.Intrinsic.Random>Operace má signaturu `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="0f67a-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="0f67a-106">Přebírá pole dvojitých hodnot jako vstup a vrátí náhodně vybraný index do pole jako `Int` .</span><span class="sxs-lookup"><span data-stu-id="0f67a-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="0f67a-107">Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu.</span><span class="sxs-lookup"><span data-stu-id="0f67a-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="0f67a-108">prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí.</span><span class="sxs-lookup"><span data-stu-id="0f67a-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="0f67a-109">Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.</span><span class="sxs-lookup"><span data-stu-id="0f67a-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
