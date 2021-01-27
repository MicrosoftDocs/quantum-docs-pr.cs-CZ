---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842523"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle – funkce

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Sestaví reflexi o daném stavu od Oracle.

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>Popis

Vzhledem k deterministickému přípravné přípravě Oracle reprezentované jednou jednotkovou maticí $O $ je výsledkem této funkce Oracle, který používá odraz kolem stavu $ \ket{\psi} $ připraveného Oracle $O $;. To znamená, že se jedná o stav $ \ket{\psi} $, který $O \ket {0} = \ket{\psi} $.

## <a name="input"></a>Vstup

### <a name="oracle--deterministicstateoracle"></a>Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Oracle, který připraví kopie stavu $ \ket{\psi} $.



## <a name="output--reflectionoracle"></a>Výstup: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Oracle, který odráží stav $ \ket{\psi} $.

## <a name="see-also"></a>Viz také

- [Microsoft..... Oracle. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft..... Oracle. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)