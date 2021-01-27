---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operace CompareUsingRippleCarry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843286"
---
# <a name="compareusingripplecarry-operation"></a>Operace CompareUsingRippleCarry

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tato operace testuje, zda celé číslo reprezentované registrem qubits je větší než jiné celé číslo, a použití funkce XOR výsledku na výstupní qubit.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Zadaná dvě celá čísla `x` a `y` uložená v qubit registrech se stejnou velikostí, tato operace kontroluje, jestli splňují `x > y` . Pokud je nastaveno na true, je 1 XORed do výstupního qubit. V opačném případě je 0 XORed do výstupního qubit.
Jinými slovy Tato operace může být reprezentována jednotkou $ $ \begin{align} U\ket {x} \ KET {y} \ KET {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.
\end{align} $ $

## <a name="input"></a>Vstup

### <a name="x--littleendian"></a>x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

První číslo, které má být porovnáno, uloženo ve `LittleEndian` formátu v qubit registru.


### <a name="y--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Druhé číslo, které má být porovnáno, uloženo ve `LittleEndian` formátu v qubit registru.


### <a name="output--qubit"></a>výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, který ukládá výsledek porovnání $x>a $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Reference

- Nové v rámci Ripple – přenést okruh Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184