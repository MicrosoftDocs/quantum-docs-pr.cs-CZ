---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: Operace GreaterThan
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707288"
---
# <a name="greaterthan-operation"></a>Operace GreaterThan

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Aplikuje větší porovnání dvou celých čísel zakódovaných do registrů qubit a Překlopí cílovou qubit na základě výsledku porovnání.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a>Popis

Provede striktně větší než porovnání dvou celých čísel $x $ a $y $ kódovaný v qubit Registry XS a y. Pokud $x > y $, qubit výsledku se překlopí, jinak se výsledek qubit.

## <a name="input"></a>Vstup

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registruje kódování prvního celého čísla $x $.


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registruje kódování druhého celého čísla $y $.


### <a name="result--qubit"></a>výsledek: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Jeden qubit, který se překlopí, pokud $x > a $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Používá štych, který $x-y = (x ' + y) ' $, kde ', kde ' označuje první doplněk.

## <a name="references"></a>Odkazy

- Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton: "nové v rámci Ripple – přenést okruh", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1

- Tomáš Haener, Martin Roetteler, Krysta M. Svore: "faktoring pomocí 2n + 2 qubits s modulární násobení Toffoli", 2016 https://arxiv.org/abs/1611.07995