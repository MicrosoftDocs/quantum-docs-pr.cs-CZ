---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834238"
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