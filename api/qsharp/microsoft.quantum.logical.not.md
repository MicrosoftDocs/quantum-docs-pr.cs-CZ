---
uid: Microsoft.Quantum.Logical.Not
title: Nefunkční
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697264"
---
# <a name="not-function"></a>Nefunkční

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček [](https://nuget.org/packages/)


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