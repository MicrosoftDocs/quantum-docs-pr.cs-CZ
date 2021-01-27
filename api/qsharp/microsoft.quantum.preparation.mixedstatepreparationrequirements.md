---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: Uživatelem definovaný typ MixedStatePreparationRequirements
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: df57b7b43fc84f7ddf68392f6a2b7013225da730
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856932"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a>Uživatelem definovaný typ MixedStatePreparationRequirements

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje počet qubits vyžadovaných pro přípravu daného smíšeného stavu.

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a>Pojmenované položky

### <a name="ntotalqubits--int"></a>NTotalQubits: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="nindexqubits--int"></a>NIndexQubits: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="ngarbagequbits--int"></a>NGarbageQubits: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="see-also"></a>Viz také

- [Microsoft. PurifiedMixedState.](xref:Microsoft.Quantum.PurifiedMixedState)