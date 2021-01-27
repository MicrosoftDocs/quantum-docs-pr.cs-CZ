---
uid: Microsoft.Quantum.Bitwise.Xor
title: XOR – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Xor
qsharp.summary: Returns the bitwise exclusive-OR (XOR) of two integers. This performs the same computation as the built-in `^^^` operator.
ms.openlocfilehash: ac31ba973ff06424dbd16168dac14a79b2691b3f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842087"
---
# <a name="xor-function"></a>XOR – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrátí bitový exkluzivní operátor OR (XOR) dvou celých čísel.
Provede se stejný výpočet jako vestavěný `^^^` operátor.

```qsharp
function Xor (a : Int, b : Int) : Int
```


## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>Příklad

```qsharp
let a = 248;       //                 11111000₂
let b = 63;        //                 00111111₂
let x = Xor(a, b); // x : Int = 199 = 11000111₂.
```

## <a name="remarks"></a>Poznámky

Další podrobnosti najdete v tématu [operátor C# ^](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) .