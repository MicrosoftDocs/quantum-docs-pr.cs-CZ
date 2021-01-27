---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operace KnillDistill
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853102"
---
# <a name="knilldistill-operation"></a>Operace KnillDistill

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="references"></a>Reference

- [Knill](https://arxiv.org/abs/quant-ph/0402171)