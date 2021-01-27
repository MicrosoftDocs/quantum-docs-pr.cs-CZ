---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Uživatelem definovaný typ ComplexPolar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847351"
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