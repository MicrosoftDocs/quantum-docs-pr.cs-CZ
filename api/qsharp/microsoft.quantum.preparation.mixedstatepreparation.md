---
uid: Microsoft.Quantum.Preparation.MixedStatePreparation
title: Uživatelem definovaný typ MixedStatePreparation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparation
qsharp.summary: Represents a particular mixed state that can be prepared on an index and a garbage register.
ms.openlocfilehash: 94d6483914b5d21bb51a5469c7123f834e9eb5da
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193569"
---
# <a name="mixedstatepreparation-user-defined-type"></a>Uživatelem definovaný typ MixedStatePreparation

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje konkrétní smíšený stav, který lze připravit na index a uvolňování paměti.

```qsharp

newtype MixedStatePreparation = (Requirements : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements, Norm : Double, Prepare : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Pojmenované položky

### <a name="requirements--mixedstatepreparationrequirements"></a>Požadavky: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)


### <a name="norm--double"></a>Norma: [Double](xref:microsoft.quantum.lang-ref.double)


### <a name="prepare--littleendianqubitqubit--unit--is-adj--ctl"></a>Prepare: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian);[qubit](xref:microsoft.quantum.lang-ref.qubit)[];[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL



## <a name="see-also"></a>Viz také

- [Microsoft. PurifiedMixedState.](xref:Microsoft.Quantum.PurifiedMixedState)