---
uid: Microsoft.Quantum.Bitwise.Not
title: Nefunkční
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Not
qsharp.summary: Returns the bitwise NOT of an integer. This performs the same computation as the built-in `~~~` operator.
ms.openlocfilehash: 9c7642770c4f1db4878ccc1aba288fb9254e017e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842113"
---
# <a name="not-function"></a>Nefunkční

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrátí bitový operátor NOT typu Integer.
Provede se stejný výpočet jako vestavěný `~~~` operátor.

```qsharp
function Not (a : Int) : Int
```


## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>Příklad

```qsharp
let a = 248;
let x = Not(a); // x : Int = -249, due to two's complement representation.
```

## <a name="remarks"></a>Poznámky

Další podrobnosti naleznete v tématu [operátor C# ~](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) .