---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 829af5424432b89adeae5243e6caac6a02f3e384
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817248"
---
# <a name="equalc-function"></a>EqualC – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--complex"></a>a: [komplexní](xref:Microsoft.Quantum.Math.Complex)

První hodnota, která se má porovnat.


### <a name="b--complex"></a>b: [komplexní](xref:Microsoft.Quantum.Math.Complex)

Druhá hodnota, která se má porovnat.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze v případě, že `a` je rovno `b` .