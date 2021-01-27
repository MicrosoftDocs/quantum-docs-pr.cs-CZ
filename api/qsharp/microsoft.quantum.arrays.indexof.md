---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848526"
---
# <a name="indexof-function"></a>IndexOf – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Příklad

Předpokládejme, že `IsEven : Int -> Bool` se jedná o funkci, která vrací `true` pouze v případě, že je její vstup i. Pak lze použít s `IndexOf` k nalezení prvního i elementu v poli:

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```