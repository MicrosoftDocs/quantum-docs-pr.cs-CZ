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
# <a name="classical-mathematical-functions"></a>Klasické matematické funkce #

Tyto funkce jsou primárně používány pro práci s vestavěnými datovými typy Q # `Int`, `Double`a `Range`.

Operace <xref:microsoft.quantum.intrinsic.random> má `(Double[] => Int)`podpisu.
Přebírá pole dvojitých hodnot jako vstup a vrací náhodně vybraný index do pole jako `Int`.
Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu. prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí.
Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.
