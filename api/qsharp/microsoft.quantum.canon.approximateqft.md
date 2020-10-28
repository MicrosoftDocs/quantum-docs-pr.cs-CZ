---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operace ApproximateQFT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704513"
---
# <a name="approximateqft-operation"></a>Operace ApproximateQFT

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použijte přibližnou neAQFTnou hodnotu Fourierova transformace () na registrační pokladnu.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
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

## <a name="references"></a>Odkazy

- [*M. Roetteler, Th. Beth* , příkaz. algebraický eng. obcí. Počítal. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv: quant-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)