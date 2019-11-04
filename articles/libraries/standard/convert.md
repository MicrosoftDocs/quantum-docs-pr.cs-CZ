---
title: 'Q # standardní knihovny – převody typu | Microsoft Docs'
description: 'Q # standardní knihovny – převody typu'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184470"
---
# <a name="type-conversions"></a><span data-ttu-id="df2e5-103">Převody typu</span><span class="sxs-lookup"><span data-stu-id="df2e5-103">Type Conversions</span></span> #

<span data-ttu-id="df2e5-104">Q # je jazyk **silného typu** .</span><span class="sxs-lookup"><span data-stu-id="df2e5-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="df2e5-105">Konkrétně Q # neumožňuje implicitně přetypování mezi různými typy.</span><span class="sxs-lookup"><span data-stu-id="df2e5-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="df2e5-106">Například `1 + 2.0` není platný výraz Q #.</span><span class="sxs-lookup"><span data-stu-id="df2e5-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="df2e5-107">Místo toho Q # poskytuje celou řadu funkcí pro převod typů pro vytváření nových hodnot daného typu.</span><span class="sxs-lookup"><span data-stu-id="df2e5-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="df2e5-108">Například <xref:microsoft.quantum.core.length> má výstupní typ `Int`, takže jeho výstup musí být nejprve převeden na `Double`, aby jej bylo možné použít jako součást výrazu s plovoucí desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="df2e5-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="df2e5-109">To lze provést pomocí funkce <xref:microsoft.quantum.convert.intasdouble>:</span><span class="sxs-lookup"><span data-stu-id="df2e5-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="df2e5-110">Obor názvů <xref:microsoft.quantum.convert> poskytuje běžné funkce pro převod typů pro práci s předdefinovanými základními typy, jako jsou `Int`, `Double`, `BigInt`, `Result`a `Bool`:</span><span class="sxs-lookup"><span data-stu-id="df2e5-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="df2e5-111">Obor názvů <xref:microsoft.quantum.convert> také poskytuje ještě více exotických převodů, jako je například `FunctionAsOperation`, které převádí funkce `'T -> 'U` na nové operace `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="df2e5-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="df2e5-112">A konečně, standardní knihovna Q # poskytuje řadu uživatelsky definovaných typů, například <xref:microsoft.quantum.math.complex> a <xref:microsoft.quantum.arithmetic.littleendian>.</span><span class="sxs-lookup"><span data-stu-id="df2e5-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="df2e5-113">Společně s těmito typy poskytuje standardní knihovna například funkce <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span><span class="sxs-lookup"><span data-stu-id="df2e5-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
