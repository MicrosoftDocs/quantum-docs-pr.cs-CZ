---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Operace ApplyQuantumFourierTransformBE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 39db7b4c69f7f06418ec257c013837c65b9cc67a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209039"
---
# <a name="applyquantumfouriertransformbe-operation"></a>Operace ApplyQuantumFourierTransformBE

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provádí operaci Fourierova transformace v rámci registru s velkým objemem, který obsahuje celé číslo v reprezentaci big-endian.

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
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