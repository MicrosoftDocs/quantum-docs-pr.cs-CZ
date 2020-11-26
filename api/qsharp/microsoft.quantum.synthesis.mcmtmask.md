---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Uživatelem definovaný typ MCMTMask
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203009"
---
# <a name="mcmtmask-user-defined-type"></a>Uživatelem definovaný typ MCMTMask

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Typ představující vícenásobnou Toffoli bránu s více cíli.

První celé číslo je bitovou maskou pro řídicí čáry.  Bitové indexy, které jsou nastaveny, odpovídají indexům řídicích čar.

Druhé celé číslo je Bitová maska pro cílové řádky.  Bitové indexy, které jsou nastaveny, odpovídají cílovým indexům řádků.

Bitové indexy obou celých čísel musí být nesouvislé.

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="controlmask--int"></a>ControlMask: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask: [int](xref:microsoft.quantum.lang-ref.int)

