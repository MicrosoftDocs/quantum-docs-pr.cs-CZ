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
ms.openlocfilehash: 55b1ef70eed1eb47ab0c6b30e2b8203c38c9a67a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833595"
---
# <a name="classical-mathematical-functions"></a>Klasické matematické funkce #

Tyto funkce jsou primárně používány pro práci s Q# vestavěnými datovými typy `Int` , `Double` a `Range` .

<xref:microsoft.quantum.intrinsic.random>Operace má signaturu `(Double[] => Int)` .
Přebírá pole dvojitých hodnot jako vstup a vrátí náhodně vybraný index do pole jako `Int` .
Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu. prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí.
Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.
