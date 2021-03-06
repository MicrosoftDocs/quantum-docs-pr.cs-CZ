---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operace ApplyXorInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843476"
---
# <a name="applyxorinplace-operation"></a>Operace ApplyXorInPlace

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operaci bitové operace-XOR mezi klasickým celým číslem a celým číslem reprezentovaným registrem qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Aplikuje `X` operace na qubits v registru s malým endian na základě 1 bitů v celé číslo.

Poznamenejte si `value` a nechť y unsigned integer kódovaný v a `target` pak `InPlaceXorLE` provede operaci určenou následující mapou: $ \ket{y}\rightarrow \ket{y\oplus a} $, kde $ \oplus $ je BITOVÝ exkluzivní operátor OR.

## <a name="input"></a>Vstup

### <a name="value--int"></a>hodnota: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo, které je považováno za nezáporné.


### <a name="target--littleendian"></a>cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registr v případě příznaku, který se používá k uložení `value` v kódování Little endian.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

