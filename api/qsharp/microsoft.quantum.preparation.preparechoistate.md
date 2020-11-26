---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Operace PrepareChoiState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: ced71c4278f42f577760acd54ae53e7f5e6dae4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210569"
---
# <a name="preparechoistate-operation"></a>Operace PrepareChoiState

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Připraví stav Choi – Jamiołkowski pro danou operaci na daný odkaz a cílové Registry.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace $ \Lambda $, jejíž Choi – Jamiołkowski State $J (\Lambda)/2 ^ N $, se připravují, kde $N $ je počet qubits, na kterých `op` působí.


### <a name="reference--qubit"></a>Referenční informace: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr qubits počínaje ve stavu $ \ket{00\cdots 0} $, který se má použít jako odkaz pro akci `op` .


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr qubits zpočátku ve stavu $ \ket{00\cdots 0} $, ve kterém se má `op` použít.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Choi – Jamiłkowski State $J (\Lambda) $ v procesu pro stav, který je definován jako $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ WHERE $ | X\rangle \! \rangle $ je *vektor* matice $X $ v konvenci pro skládání sloupců. Výuková klasická Popis tohoto stavu poskytuje úplné informace o účinku $ \Lambda $ v libovolných vstupních stavech a tvoří základ pro *tomography procesu*.

## <a name="see-also"></a>Viz také

- [Microsoft. Přípravno. Preparation. PrepareChoiStateA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft. Přípravno. Preparation. PrepareChoiStateC](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft. Přípravno. Preparation. PrepareChoiStateCA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)