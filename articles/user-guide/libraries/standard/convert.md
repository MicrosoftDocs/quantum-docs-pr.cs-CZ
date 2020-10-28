---
title: Převody typů ve Q# standardních knihovnách
description: Přečtěte si o běžných a uživatelsky definovaných funkcích pro převod typu ve Q# standardních knihovnách.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691098"
---
# <a name="type-conversions"></a>Převody typu #

Q# je jazyk **silného typu** .
Konkrétně neumožňuje Q# implicitně přetypování mezi různými typy. Například `1 + 2.0` není platný Q# výraz.
Místo toho Q# poskytuje celou řadu funkcí pro převod typů pro vytváření nových hodnot daného typu.

Například <xref:Microsoft.Quantum.Core.Length> má výstupní typ `Int` , takže jeho výstup musí být nejprve převeden na a předtím, aby `Double` jej bylo možné použít jako součást výrazu s plovoucí desetinnou čárkou.
To lze provést pomocí <xref:Microsoft.Quantum.Convert.IntAsDouble> funkce:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:Microsoft.Quantum.Convert>Obor názvů poskytuje běžné funkce pro převod typů pro práci s předdefinovanými základními typy, jako jsou,,, `Int` `Double` `BigInt` `Result` a `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:Microsoft.Quantum.Convert>Obor názvů také poskytuje ještě více exotických převodů, například `FunctionAsOperation` , které převádí funkce `'T -> 'U` na nové operace `'T => 'U` .

Nakonec Q# Standardní knihovna poskytuje řadu uživatelsky definovaných typů, jako jsou <xref:Microsoft.Quantum.Math.Complex> a <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .
Společně s těmito typy poskytuje standardní knihovna například tyto funkce <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
