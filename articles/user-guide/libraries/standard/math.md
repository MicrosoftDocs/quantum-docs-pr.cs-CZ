---
title: Matematické Q# standardní knihovny
description: Přečtěte si o klasických matematických funkcích ve Q# standardních knihovnách, které se používají s vestavěnými datovými typy.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692060"
---
# <a name="classical-mathematical-functions"></a>Klasické matematické funkce #

Tyto funkce jsou primárně používány pro práci s Q# vestavěnými datovými typy `Int` , `Double` a `Range` .

<xref:Microsoft.Quantum.Intrinsic.Random>Operace má signaturu `(Double[] => Int)` .
Přebírá pole dvojitých hodnot jako vstup a vrátí náhodně vybraný index do pole jako `Int` .
Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu. prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí.
Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.
