---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operace MeasureInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707176"
---
# <a name="measureinteger-operation"></a>Operace MeasureInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


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