---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 83bf5ba245038ad1c7c6ed4e8cdb493317276e6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817165"
---
# <a name="equalcp-function"></a>EqualCP – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--complexpolar"></a>Odpověď: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

První hodnota, která se má porovnat.


### <a name="b--complexpolar"></a>b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Druhá hodnota, která se má porovnat.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze v případě, že `a` je rovno `b` .