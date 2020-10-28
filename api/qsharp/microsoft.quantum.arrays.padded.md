---
uid: Microsoft.Quantum.Arrays.Padded
title: Čalouněná funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705849"
---
# <a name="padded-function"></a>Čalouněná funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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