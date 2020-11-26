---
uid: Microsoft.Quantum.Arrays.Padded
title: Čalouněná funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220531"
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