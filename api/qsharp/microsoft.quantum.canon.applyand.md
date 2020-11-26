---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Operace ApplyAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: b749013584c89273375da002ac36b3575085b7f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219290"
---
# <a name="applyand-operation"></a>Operace ApplyAnd

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Invertuje zadaný cílový qubit, pokud jsou oba ovládací prvky qubits ve 1 stavu, přičemž pomocí měření provede operaci sousedících operací.

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Invertuje `target` pouze v případě, že jsou oba ovládací prvky 1, ale předpokládá, že `target` je ve stavu 0.  Operace má T-Count 4, T-Depth 2 a nevyžaduje žádné pomocné qubit a může proto být vhodnější pro operaci CCNOT, pokud `target` je známo, že má hodnotu 0.  Sousední operace této operace měří na základě měření a nevyžaduje žádné brány T.

Kontrolované použití této operace nevyžaduje žádné pomocné qubit, `2^c` `Rz` brány a není optimalizované pro hloubku, kde `c` je počet celkových ovládacích prvků qubits, včetně dvou ovládacích prvků z `ApplyAnd` operace.  Aplikace řízená pomocí souseda vyžaduje, aby byly `2^c - 1` `Rz` brány (s úhlem dvojnásobku velikosti nesousedících operací), žádné pomocné qubit a není optimalizované pro hloubku.

## <a name="input"></a>Vstup

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit prvního ovládacího prvku


### <a name="control2--qubit"></a>Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druhý qubit ovládacího prvku


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Cílová pomocná qubit; musí být ve stavu 0.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Reference

- Cody Novotný: "nové konstrukce pro bránu Toffoli odolné proti chybám", fyz. rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA. 87.022328
- Craig Gidney: "snížení nákladů na sčítání, 2. stranu, strana 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) doi: 10.1103/PhysRevA. 85.044302
- Mathias Soeken: "okruhy Oracle a vzor vánoční stromové struktury", [článek na blogu od 19. prosince 2019](https://msoeken.github.io/blog_qac.html) (Poznámka: vysvětlení více řízených konstrukcí)