---
uid: Microsoft.Quantum.Arrays.Chunks
title: Funkce bloků dat
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221602"
---
# <a name="chunks-function"></a>Funkce bloků dat

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rozdělí pole na více částí stejné délky.

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Vstup

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)

Délka každého bloku.


### <a name="arr--t"></a>Šipka: t []

Pole, které má být rozděleno.



## <a name="output--t"></a>Výstup: t [] []

Pole obsahující všechny bloky původního pole.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Všimněte si, že poslední element výstupu může být kratší než, `nElements` Pokud není `Length(arr)` dělitelem `nElements` .