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
# <a name="type-conversions"></a><span data-ttu-id="44b48-103">Převody typu</span><span class="sxs-lookup"><span data-stu-id="44b48-103">Type Conversions</span></span> #

<span data-ttu-id="44b48-104">Q # je jazyk **silného typu** .</span><span class="sxs-lookup"><span data-stu-id="44b48-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="44b48-105">Konkrétně Q # neumožňuje implicitně přetypování mezi různými typy.</span><span class="sxs-lookup"><span data-stu-id="44b48-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="44b48-106">Například není `1 + 2.0` platný výraz Q #.</span><span class="sxs-lookup"><span data-stu-id="44b48-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="44b48-107">Místo toho Q # poskytuje celou řadu funkcí pro převod typů pro vytváření nových hodnot daného typu.</span><span class="sxs-lookup"><span data-stu-id="44b48-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="44b48-108">Například <xref:microsoft.quantum.core.length> má výstupní typ `Int` , takže jeho výstup musí být nejprve převeden na a předtím, aby `Double` jej bylo možné použít jako součást výrazu s plovoucí desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="44b48-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="44b48-109">To lze provést pomocí <xref:microsoft.quantum.convert.intasdouble> funkce:</span><span class="sxs-lookup"><span data-stu-id="44b48-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="44b48-110"><xref:microsoft.quantum.convert>Obor názvů poskytuje běžné funkce pro převod typů pro práci s předdefinovanými základními typy, jako jsou,,, `Int` `Double` `BigInt` `Result` a `Bool` :</span><span class="sxs-lookup"><span data-stu-id="44b48-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="44b48-111"><xref:microsoft.quantum.convert>Obor názvů také poskytuje ještě více exotických převodů, například `FunctionAsOperation` , které převádí funkce `'T -> 'U` na nové operace `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="44b48-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="44b48-112">Nakonec standardní knihovna Q # poskytuje řadu uživatelsky definovaných typů, jako jsou <xref:microsoft.quantum.math.complex> a <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="44b48-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="44b48-113">Společně s těmito typy poskytuje standardní knihovna například tyto funkce <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :</span><span class="sxs-lookup"><span data-stu-id="44b48-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
