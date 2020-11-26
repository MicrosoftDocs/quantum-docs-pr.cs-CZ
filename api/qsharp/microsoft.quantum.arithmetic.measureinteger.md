---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operace MeasureInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222639"
---
# <a name="measureinteger-operation"></a>Operace MeasureInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Měří obsah v registru a převede ho na celé číslo. Měření se provádí s ohledem na standardní výpočetní základ, tj. eigenbasis `PauliZ` .

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>Vstup

### <a name="target--littleendian"></a>cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

V rámci kódování ve Little endian se registruje.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Unsigned integer obsahující měřenou hodnotu `target` .

## <a name="remarks"></a>Poznámky

Tato operace obnoví vstupní registr do stavu $ \ket{00\cdots 0} $, který je vhodný pro uvolnění zpět na cílový počítač.

## <a name="see-also"></a>Viz také

- [Microsoft. proMeasureIntegerBE. Canon.](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)