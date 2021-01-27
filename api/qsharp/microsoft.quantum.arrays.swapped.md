---
uid: Microsoft.Quantum.Arrays.Swapped
title: Swap – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850953"
---
# <a name="swapped-function"></a>Swap – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije záměnu dvou prvků v poli.

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="firstindex--int"></a>firstIndex: [int](xref:microsoft.quantum.lang-ref.int)

Index prvního prvku, který má být prohozen.


### <a name="secondindex--int"></a>secondIndex: [int](xref:microsoft.quantum.lang-ref.int)

Index druhého elementu, který se má zaměnit


### <a name="arr--t"></a>Šipka: t []

Pole s prvky, které mají být prohozeny.



## <a name="output--t"></a>Výstup: t []

Pole s použitým přepnutím na místě

## <a name="example"></a>Příklad

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

