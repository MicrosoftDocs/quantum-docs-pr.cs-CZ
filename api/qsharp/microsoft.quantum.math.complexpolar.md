---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Uživatelem definovaný typ ComplexPolar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210977"
---
# <a name="complexpolar-user-defined-type"></a>Uživatelem definovaný typ ComplexPolar

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje komplexní číslo v polárním tvaru.

Polární reprezentace komplexního čísla je $c = r e ^ {i t} $.

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="magnitude--double"></a>Velikost: [Double](xref:microsoft.quantum.lang-ref.double)

Absolutní hodnota $r \ge $0 z $c $.
### <a name="argument--double"></a>Argument: [Double](xref:microsoft.quantum.lang-ref.double)

Fáze $t \in \mathbb R $ of $c $.