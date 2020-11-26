---
uid: Microsoft.Quantum.Logical.Not
title: Nefunkční
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197445"
---
# <a name="not-function"></a>Nefunkční

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí logickou negaci hodnoty.

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>Vstup

### <a name="value--bool"></a>hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)

Hodnota, která má být negace.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze v případě, že `value` je `false` .

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```Q#
let x = not value;
let x = Not(value);
```