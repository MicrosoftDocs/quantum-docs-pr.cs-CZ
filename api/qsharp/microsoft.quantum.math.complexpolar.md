---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Uživatelem definovaný typ ComplexPolar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697201"
---
# <a name="complexpolar-user-defined-type"></a>Uživatelem definovaný typ ComplexPolar

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček [](https://nuget.org/packages/)


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