---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operace MeasureInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843110"
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