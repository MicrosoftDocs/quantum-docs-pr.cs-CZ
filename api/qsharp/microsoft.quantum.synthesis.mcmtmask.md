---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Uživatelem definovaný typ MCMTMask
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855373"
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

