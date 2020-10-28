---
uid: Microsoft.Quantum.Arrays.Chunks
title: Funkce bloků dat
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706176"
---
# <a name="chunks-function"></a>Funkce bloků dat

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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