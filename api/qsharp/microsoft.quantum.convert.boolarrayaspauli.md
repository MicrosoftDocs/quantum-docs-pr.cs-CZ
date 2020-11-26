---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214275"
---
# <a name="boolarrayaspauli-function"></a>BoolArrayAsPauli – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


V případě bitového řetězce vrátí operátor qubit Pauli, který je reprezentován jako pole operátorů s jedním qubit Pauli.

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>Vstup

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli operátor, který se má použít pro qubits, kde `bitsApply == bits[idx]` .


### <a name="bitapply--bool"></a>bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)

Pokud je tato hodnota bit, použijte Pauli.


### <a name="bits--bool"></a>bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Pole Boolean.



## <a name="output--pauli"></a>Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>Poznámky

Pole Boolean a registr s police musí mít stejnou délku.