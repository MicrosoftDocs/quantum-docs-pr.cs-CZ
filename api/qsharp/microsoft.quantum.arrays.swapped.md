---
uid: Microsoft.Quantum.Arrays.Swapped
title: Swap – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 173fb32b5a41ce054f19548a7fcca18c11c4c4cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220123"
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

