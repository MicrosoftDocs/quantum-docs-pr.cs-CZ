---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 47e8a74d3631be2209537679ec9786a8dab63c58
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200777"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn – funkce

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí funkci, která mapuje Syndrome o chybách na odpovídající chybu – správné správnosti Paulich operátorů podle vyhledávání v tabulce pro kód ⟦ 5, 1, 3 ⟧.

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Výstup: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Funkce typu `RecoveryFn` , která přijímá Syndrome měření `Result[]` a vrací `Pauli[]` operátory, které opraví zjištěnou chybu.

## <a name="remarks"></a>Poznámky

Díky iteraci všech chyb s váhou $1 $ získáme celkem $3 \ krát 5 = 15 $ možné netriviální Syndromes.
Společně s identitou je sestavena tabulka Error a odpovídající Syndrome. Pro kód 5 qubit, na který je tato tabulka dána: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); × \_ 3: (1, 1, 0, 0); × \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ s $Y _i $ získá přidáním $X _i $ a $Z _i $ Syndromes. Všimněte si, že pořadí při obnovení tabulky je předané převedením bitvectors na celá čísla (s použitím Little Endian).

## <a name="see-also"></a>Viz také

- [Microsoft. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)