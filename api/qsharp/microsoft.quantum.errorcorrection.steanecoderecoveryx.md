---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 5fac832ef5b7d7be2d85675a32f45e66312f66c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200366"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX – funkce

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dekodér pro X-část skupiny stabilizace kódu ⟦ 7, 1, 3 ⟧ Steane.

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>Vstup

### <a name="syndrome--syndrome"></a>Syndrome: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Pole Syndrome získané z měření X-části stabilizovaného modulu.



## <a name="output--pauli"></a>Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pole Pauli operací, které při použití s kódovaným systémem v-opravuje chybu odpovídající `syndrome` .

## <a name="remarks"></a>Poznámky

Zvolený dekodér používá vlastnost kódu CSS kódu ⟦ 7, 1, 3 ⟧ Steane, to znamená, že opraví chyby X a chyby Z samostatně. Vlastnost kódu je, že umístění X, v uvedeném pořadí má být použito, je trojrozměrné kódování X, v tomto pořadí Z Syndrome, pokud se považuje za celé číslo.

## <a name="references"></a>Reference

- D. Gottesman, "kódy stabilizovaných a chybových stavů," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Viz také

- [Microsoft. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. ErrorCorrection. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)