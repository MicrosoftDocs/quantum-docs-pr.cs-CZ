---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operace ApproximateQFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850327"
---
# <a name="approximateqft-operation"></a>Operace ApproximateQFT

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použijte přibližnou neAQFTnou hodnotu Fourierova transformace () na registrační pokladnu.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

parametr aproximace, který určuje, na jaké úrovni se vyřadí kontrolované otočení Z okruhu QFT.

Parametr aproximace a určuje úroveň vyřazení z rotací, tj. ∈ {0.. n} a všech rotací Z 2π/2k, kde k>a jsou odebrány z okruhu QFT. Je známo, že pro k >= log ₂ (n) + log ₂ (1/ε) + 3 jedna se dá svázat | | QFT-AQFT | |<ε.


### <a name="qs--bigendian"></a>QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

registruje se v registru n qubits, na které se použije Přibližná transformace pro Fourierova množství.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

AQFT vyžaduje pro 2π/2k a Hadamard brány v rámci rotace.

Předpokládá se, že vstup a výstup se zakódují do kódování ve formátu big endian.

## <a name="references"></a>Reference

- [*M. Roetteler, Th. Beth*, příkaz. algebraický eng. obcí. Počítal. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv: quant-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)