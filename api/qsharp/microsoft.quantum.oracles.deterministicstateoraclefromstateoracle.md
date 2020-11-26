---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 183b1108ead6239e26bb0b38144cb9374e7bf285
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226753"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle – funkce

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Převede typ Oracle typu `StateOracle` na `DeterministicStateOracle` .

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a>Vstup

### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Index na příznak qubit `stateOracle` $A $, který explicitně funguje na dvou registrech: příznak $f $ a systém $s $, např. $A \ket {0} \_ f\ket {\ psí} \_ s $.


### <a name="stateoracle--stateoracle"></a>stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Příprava stavu Oracle $A $ typu `StateOracle` .



## <a name="output--deterministicstateoracle"></a>Výstup: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Stejný stav přípravy Oracle $A $, ale nyní `DeterministicStateOracle` je typ, takže funguje v registru, kde $a, s $ již explicitně neoddělené, např.  $A \ket{0\psi} \_ {as} $.

## <a name="see-also"></a>Viz také

- [Microsoft..... Oracle. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)
- [Microsoft..... Oracle. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)