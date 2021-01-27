---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842541"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete – funkce

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vzhledem k tomu, že operace představující "černé pole" je Oracle, vrátí nediskrétní Oracle, který představuje "černý rámeček" Oracle se opakuje několikrát.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Vstup

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operace, která má být exponentiated.



## <a name="output--discreteoracle"></a>Výstup: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operace se částečně nastavila na "černém" poli Oracle, které představuje diskrétní čas Oracle.

## <a name="example"></a>Příklad

`OracleToDiscrete(U)(3, target)` odpovídá `U(target)` opakování třikrát.