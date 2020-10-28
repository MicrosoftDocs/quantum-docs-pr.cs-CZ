---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Operace ApplyQuantumFourierTransform
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: fa8d135c0665f0a576229797d208b321ba0329a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705097"
---
# <a name="applyquantumfouriertransform-operation"></a>Operace ApplyQuantumFourierTransform

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Provádí operaci Fourierova transformace v registru s jednou hodnotou, která obsahuje celé číslo v reprezentaci Little-endian.

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Vstup

### <a name="qs--littleendian"></a>QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registrování v registru, na které se používá Fourierova transformace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

U vstupu a výstupu se předpokládá kódování ve Little endian.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyQuantumFourierTransformBE. Canon.](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)