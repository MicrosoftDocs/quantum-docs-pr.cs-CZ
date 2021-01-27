---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Operace ApproximatelyMultiplexZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: b69b4de62241a7d16c2f07449115f864defda45d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841093"
---
# <a name="approximatelymultiplexz-operation"></a>Operace ApproximatelyMultiplexZ

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje Pauli Z rotace v poli qubits a zkrátí krátké úhly otočení na základě dané tolerance.

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

To platí pro vynásobenou jednotnou operaci, která provádí rotace pomocí úhlu $ \ theta_j $ o qubit Pauli operator $Z $, pokud je kontrolováno stavem $n $-qubit číslo $ \ket{j} $.
Konkrétně tuto operaci může představovat jednotná

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.
\end{align} $ $

## <a name="input"></a>Vstup

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerance, pod kterou jsou malé koeficienty zkráceny.


### <a name="coefficients--double"></a>koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole až do $2 ^ n $ koeficienty $ \ theta_j $. $J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.


### <a name="control--littleendian"></a>ovládací prvek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Jeden qubit registr, který je otočen $e ^ {i P \ theta_j} $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

`coefficients` budou doplněny elementy $ \ theta_j = $0,0, pokud je zadána méně než $2 ^ n $.

## <a name="references"></a>Reference

- Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Viz také

- [Microsoft. proMultiplexZ. Canon.](xref:Microsoft.Quantum.Canon.MultiplexZ)