---
title: Převody typů ve Q# standardních knihovnách
description: Přečtěte si o běžných a uživatelsky definovaných funkcích pro převod typu ve Q# standardních knihovnách.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2319bf453f5fbf6bd068859ea65562423d3ff4d0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868505"
---
# <a name="type-conversions"></a>Převody typu #

Q#je jazyk **silného typu** .
Konkrétně neumožňuje Q# implicitně přetypování mezi různými typy. Například `1 + 2.0` není platný Q# výraz.
Místo toho Q# poskytuje celou řadu funkcí pro převod typů pro vytváření nových hodnot daného typu.

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

Nakonec Q# Standardní knihovna poskytuje řadu uživatelsky definovaných typů, jako jsou <xref:microsoft.quantum.math.complex> a <xref:microsoft.quantum.arithmetic.littleendian> .
Společně s těmito typy poskytuje standardní knihovna například tyto funkce <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
