---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operace ApplyXorInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707457"
---
# <a name="applyxorinplace-operation"></a>Operace ApplyXorInPlace

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci bitové operace-XOR mezi klasickým celým číslem a celým číslem reprezentovaným registrem qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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

