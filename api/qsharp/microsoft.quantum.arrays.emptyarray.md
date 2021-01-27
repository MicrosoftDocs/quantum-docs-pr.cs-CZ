---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846177"
---
# <a name="emptyarray-function"></a>EmptyArray – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrátí prázdné pole daného typu.

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>Výstup: ' TElement []

Prázdné pole

## <a name="type-parameters"></a>Parametry typu

### <a name="telement"></a>'TElement

Typ prvků pole.

## <a name="example"></a>Příklad

```qsharp
let empty = EmptyArray<Int>();
```