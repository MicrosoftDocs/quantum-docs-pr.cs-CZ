---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operace ApplyXorInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210106"
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

