---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funkce inřazení
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845735"
---
# <a name="issorted-function"></a>Funkce inřazení

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


V případě pole, vrátí, zda je toto pole řazeno tak, jak je definováno danou funkcí porovnání.

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Vstup

### <a name="comparison--tt---bool"></a>porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce, která porovná dva prvky, například, že jsou `a` považovány za menší nebo rovny, `b` Pokud `comparison(a, b)` je `true` .


### <a name="array--t"></a>Array: t []

Pole, které se má zkontrolovat



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Pokud a pouze pokud pro každou dvojici prvků `a` a `b` výskyt `array` v tomto pořadí, `comparison(a, b)` je `true` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `array` .

## <a name="remarks"></a>Poznámky

Tato funkce `comparison` je považována za přenositelný, takže pokud `comparison(a, b)` a `comparison(b, c)` , pak `comparison(a, c)` se předpokládá. Pokud tato vlastnost není uložena, bude výstup této funkce pravděpodobně nesprávný.