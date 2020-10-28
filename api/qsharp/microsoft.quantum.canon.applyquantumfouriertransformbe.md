---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Operace ApplyQuantumFourierTransformBE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705096"
---
# <a name="applyquantumfouriertransformbe-operation"></a>Operace ApplyQuantumFourierTransformBE

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Provádí operaci Fourierova transformace v rámci registru s velkým objemem, který obsahuje celé číslo v reprezentaci big-endian.

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Vstup

### <a name="qs--bigendian"></a>QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registrování v registru, na které se používá Fourierova transformace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

U vstupu a výstupu se předpokládá, že jsou v kódování big endian.

## <a name="see-also"></a>Viz také

- [Microsoft. proApproximateQFT. Canon.](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [Microsoft. proQFTLE. Canon.](xref:Microsoft.Quantum.Canon.QFTLE)