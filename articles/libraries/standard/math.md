---
title: 'Q # standardní knihovny – matematické | Microsoft Docs'
description: 'Q # standardní knihovny – matematické'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184453"
---
# <a name="classical-mathematical-functions"></a>Klasické matematické funkce #

Tyto funkce jsou primárně používány pro práci s vestavěnými datovými typy Q # `Int`, `Double`a `Range`.

Operace <xref:microsoft.quantum.intrinsic.random> má `(Double[] => Int)`podpisu.
Přebírá pole dvojitých hodnot jako vstup a vrací náhodně vybraný index do pole jako `Int`.
Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu. prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí.
Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.