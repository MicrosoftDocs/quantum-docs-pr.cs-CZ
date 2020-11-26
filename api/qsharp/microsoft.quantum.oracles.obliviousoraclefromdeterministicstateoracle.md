---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 8f1fe34e38edefba228fb9d01e1712e4c0916970
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226685"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a>ObliviousOracleFromDeterministicStateOracle – funkce

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kombinuje Oracle `DeterministicStateOracle` a `ObliviousOracle` .

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a>Vstup

### <a name="ancillaoracle--deterministicstateoracle"></a>ancillaOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Příprava stavu Oracle $A $, `DeterministicStateOracle` který působí v registru $a $.


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Typ Oracle $U $ `ObliviousOracle` pracuje společně s registrací $a, s $.



## <a name="output--obliviousoracle"></a>Výstup: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Typ Oracle $O = UA $ typu `ObliviousOracle` .

## <a name="see-also"></a>Viz také

- [Microsoft..... Oracle. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft..... Oracle. ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)