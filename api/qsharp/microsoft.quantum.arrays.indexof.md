---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705977"
---
# <a name="indexof-function"></a>IndexOf – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Vrátí první index prvního prvku v poli, který splňuje daný predikát. Pokud žádný takový prvek neexistuje, vrátí hodnotu-1.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Vstup

### <a name="predicate--t---bool"></a>predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce predikátu, která funguje na prvcích pole.


### <a name="arr--t"></a>Šipka: t []

Pole, které má být prohledáno pomocí daného predikátu.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Buď nejmenší index, `idx` který `predicate(arr[idx])` je true, nebo-1, pokud žádný takový prvek neexistuje.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

