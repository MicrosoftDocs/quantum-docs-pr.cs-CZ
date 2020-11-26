---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Operace ApplyQuantumFourierTransform
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 6d3ad9ca2e0d10c264f8020e1f34687f6cbc9f94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218185"
---
# <a name="applyquantumfouriertransform-operation"></a>Operace ApplyQuantumFourierTransform

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provádí operaci Fourierova transformace v registru s jednou hodnotou, která obsahuje celé číslo v reprezentaci Little-endian.

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="qs--littleendian"></a>QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registrování v registru, na které se používá Fourierova transformace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

U vstupu a výstupu se předpokládá kódování ve Little endian.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyQuantumFourierTransformBE. Canon.](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)