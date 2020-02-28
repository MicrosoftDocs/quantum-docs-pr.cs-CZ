---
title: 'Převody typů ve standardních knihovnách Q #'
description: 'Přečtěte si o běžných a uživatelsky definovaných funkcích pro převod typu v knihovnách Q # Standard.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907796"
---
# <a name="type-conversions"></a>Převody typu #

Q # je jazyk **silného typu** .
Konkrétně Q # neumožňuje implicitně přetypování mezi různými typy. Například `1 + 2.0` není platný výraz Q #.
Místo toho Q # poskytuje celou řadu funkcí pro převod typů pro vytváření nových hodnot daného typu.

Například <xref:microsoft.quantum.core.length> má výstupní typ `Int`, takže jeho výstup musí být nejprve převeden na `Double`, aby jej bylo možné použít jako součást výrazu s plovoucí desetinnou čárkou.
To lze provést pomocí funkce <xref:microsoft.quantum.convert.intasdouble>:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

Obor názvů <xref:microsoft.quantum.convert> poskytuje běžné funkce pro převod typů pro práci s předdefinovanými základními typy, jako jsou `Int`, `Double`, `BigInt`, `Result`a `Bool`:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

Obor názvů <xref:microsoft.quantum.convert> také poskytuje ještě více exotických převodů, jako je například `FunctionAsOperation`, které převádí funkce `'T -> 'U` na nové operace `'T => 'U`.

A konečně, standardní knihovna Q # poskytuje řadu uživatelsky definovaných typů, například <xref:microsoft.quantum.math.complex> a <xref:microsoft.quantum.arithmetic.littleendian>.
Společně s těmito typy poskytuje standardní knihovna například funkce <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
