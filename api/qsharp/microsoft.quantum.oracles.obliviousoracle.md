---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Uživatelem definovaný typ ObliviousOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842550"
---
# <a name="obliviousoracle-user-defined-type"></a>Uživatelem definovaný typ ObliviousOracle

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje systém Oracle pro zesílení amplitud oblivious.

Vstupy pro Oracle $O $ jsou:

- Registr ancilla $a $, na kterém $O $ funguje.
- Registr systému $s $, na kterém se aplikuje požadovaná Jednotková $U $, po vybírání v registru $a $ se ve stavu $ \ket{t} \_ a $.

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Poznámky

Tento jazyk Oracle definovaný pomocí $ $ O\ket {s} \_ a\ket {\ psí} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ funguje ve stavu ancilla $ \ket{s} \_ a, který implementuje jednotkové $U $ v jakémkoli stavu systému $ \ket{\psi} \_ s $ s amplitudou $ \lambda $ v souladu s příznakem $ \ket{t} \_ a $.
Prvním parametrem je qubit registr $ \ket{s} \_ a $. Druhým parametrem je qubit registr $ \ket{\psi} \_ s $.