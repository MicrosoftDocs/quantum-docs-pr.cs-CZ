---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Uživatelem definovaný typ ReflectionOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854487"
---
# <a name="reflectionoracle-user-defined-type"></a>Uživatelem definovaný typ ReflectionOracle

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje reflexi Oracle.

Reflexe Oracle, $O $, má vstupy:

- Fáze $ \phi $, o kterou se má otočit odrážet mezera.
- Registr qubit, na kterém se má provést daná reflexe.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Pojmenované položky

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL



## <a name="remarks"></a>Poznámky

Tento Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ provede částečný odraz pomocí fáze $ \phi $ o jednom čistě stavu $ \ket{\psi} $.