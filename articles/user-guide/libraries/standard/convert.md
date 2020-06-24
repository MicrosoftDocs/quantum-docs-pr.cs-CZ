---
title: 'Převody typů ve standardních knihovnách Q #'
description: 'Přečtěte si o běžných a uživatelsky definovaných funkcích pro převod typu v knihovnách Q # Standard.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274614"
---
# <a name="type-conversions"></a>Převody typu #

Q # je jazyk **silného typu** .
Konkrétně Q # neumožňuje implicitně přetypování mezi různými typy. Například není `1 + 2.0` platný výraz Q #.
Místo toho Q # poskytuje celou řadu funkcí pro převod typů pro vytváření nových hodnot daného typu.

Například <xref:microsoft.quantum.core.length> má výstupní typ `Int` , takže jeho výstup musí být nejprve převeden na a předtím, aby `Double` jej bylo možné použít jako součást výrazu s plovoucí desetinnou čárkou.
To lze provést pomocí <xref:microsoft.quantum.convert.intasdouble> funkce:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert>Obor názvů poskytuje běžné funkce pro převod typů pro práci s předdefinovanými základními typy, jako jsou,,, `Int` `Double` `BigInt` `Result` a `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert>Obor názvů také poskytuje ještě více exotických převodů, například `FunctionAsOperation` , které převádí funkce `'T -> 'U` na nové operace `'T => 'U` .

Nakonec standardní knihovna Q # poskytuje řadu uživatelsky definovaných typů, jako jsou <xref:microsoft.quantum.math.complex> a <xref:microsoft.quantum.arithmetic.littleendian> .
Společně s těmito typy poskytuje standardní knihovna například tyto funkce <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
