---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operace KnillDistill
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697953"
---
# <a name="knilldistill-operation"></a>Operace KnillDistill

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček [](https://nuget.org/packages/)


Implementuje algoritmus Knill Magic State.

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>Popis

Vzhledem k 15 přibližným kopiím stavu Magic $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} \end{align}, $ $ vytvoří jednu kopii s vyšší kvalitou.

## <a name="input"></a>Vstup

### <a name="roughmagic--qubit"></a>roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr 15 qubits obsahujících přibližné kopie stavu Magic. Po použití tohoto postupu je potřeba, aby `roughMagic[0]` obsahovalo jednu kopii s vyšší kvalitou a zbytek registru se resetoval na stav $ \ket{00\cdots 0} $.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

Pokud byl `true` postup úspěšný a je třeba přijmout kopii vyšší kvality. Pokud `false` se procedura nezdařila a stav registru by měl být považován za nedefinovaný.

## <a name="remarks"></a>Poznámky

Sledujeme algoritmus Knill.
Nicméně Současná implementace je daleko od optimálního, protože používá příliš mnoho qubits.
V této rutině jsou vloženy stavy Magic. v takovém případě jsou k dispozici lepší protokoly.

## <a name="references"></a>Odkazy

- [Knill](https://arxiv.org/abs/quant-ph/0402171)