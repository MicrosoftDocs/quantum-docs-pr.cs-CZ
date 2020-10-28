---
title: 'Převody typů ve :::no-loc(Q#)::: standardních knihovnách'
description: 'Přečtěte si o běžných a uživatelsky definovaných funkcích pro převod typu ve :::no-loc(Q#)::: standardních knihovnách.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691098"
---
# <a name="type-conversions"></a><span data-ttu-id="5cb4b-103">Převody typu</span><span class="sxs-lookup"><span data-stu-id="5cb4b-103">Type Conversions</span></span> #

<span data-ttu-id="5cb4b-104">:::no-loc(Q#)::: je jazyk **silného typu** .</span><span class="sxs-lookup"><span data-stu-id="5cb4b-104">:::no-loc(Q#)::: is a **strongly-typed** language.</span></span>
<span data-ttu-id="5cb4b-105">Konkrétně neumožňuje :::no-loc(Q#)::: implicitně přetypování mezi různými typy.</span><span class="sxs-lookup"><span data-stu-id="5cb4b-105">In particular, :::no-loc(Q#)::: does not implicitly cast between distinct types.</span></span> <span data-ttu-id="5cb4b-106">Například `1 + 2.0` není platný :::no-loc(Q#)::: výraz.</span><span class="sxs-lookup"><span data-stu-id="5cb4b-106">For instance, `1 + 2.0` is not a valid :::no-loc(Q#)::: expression.</span></span>
<span data-ttu-id="5cb4b-107">Místo toho :::no-loc(Q#)::: poskytuje celou řadu funkcí pro převod typů pro vytváření nových hodnot daného typu.</span><span class="sxs-lookup"><span data-stu-id="5cb4b-107">Rather, :::no-loc(Q#)::: provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="5cb4b-108">Například <xref:Microsoft.Quantum.Core.Length> má výstupní typ `Int` , takže jeho výstup musí být nejprve převeden na a předtím, aby `Double` jej bylo možné použít jako součást výrazu s plovoucí desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="5cb4b-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="5cb4b-109">To lze provést pomocí <xref:Microsoft.Quantum.Convert.IntAsDouble> funkce:</span><span class="sxs-lookup"><span data-stu-id="5cb4b-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="5cb4b-110"><xref:Microsoft.Quantum.Convert>Obor názvů poskytuje běžné funkce pro převod typů pro práci s předdefinovanými základními typy, jako jsou,,, `Int` `Double` `BigInt` `Result` a `Bool` :</span><span class="sxs-lookup"><span data-stu-id="5cb4b-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="5cb4b-111"><xref:Microsoft.Quantum.Convert>Obor názvů také poskytuje ještě více exotických převodů, například `FunctionAsOperation` , které převádí funkce `'T -> 'U` na nové operace `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="5cb4b-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="5cb4b-112">Nakonec :::no-loc(Q#)::: Standardní knihovna poskytuje řadu uživatelsky definovaných typů, jako jsou <xref:Microsoft.Quantum.Math.Complex> a <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="5cb4b-112">Finally, the :::no-loc(Q#)::: standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="5cb4b-113">Společně s těmito typy poskytuje standardní knihovna například tyto funkce <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="5cb4b-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```:::no-loc(Q#):::
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
