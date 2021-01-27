---
uid: Microsoft.Quantum.Logical.Not
title: Nefunkční
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849077"
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

```qsharp
let x = not value;
let x = Not(value);
```