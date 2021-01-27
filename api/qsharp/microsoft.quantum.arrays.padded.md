---
uid: Microsoft.Quantum.Arrays.Padded
title: Čalouněná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845569"
---
# <a name="padded-function"></a>Čalouněná funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí pole doplněné o zadané hodnoty až po zadanou délku.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="nelementstotal--int"></a>nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)

Délka čalouněného pole. Pokud je to pozitivní, `inputArray` je doplněna na hlavu. Pokud je tato hodnota záporná, `inputArray` je doplněna na konec.


### <a name="defaultelement--t"></a>defaultElement: 'T

Výchozí hodnota, která se má použít pro prvky odsazení


### <a name="inputarray--t"></a>inputArray: t []

Pole, jehož hodnoty jsou na začátku výstupního pole.



## <a name="output--t"></a>Výstup: t []

Pole `output` , které je `inputArray` doplněno na hlavu s s `defaultElement` až do `output` délky `nElementsTotal`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvků pole.

## <a name="example"></a>Příklad

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```