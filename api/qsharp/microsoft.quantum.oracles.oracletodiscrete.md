---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193841"
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