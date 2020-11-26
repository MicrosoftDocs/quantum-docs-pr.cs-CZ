---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 4c511489888613d95adaf154c005b3211af75446
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198380"
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