---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operace DumpOperation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829284"
---
# <a name="dumpoperation-operation"></a>Operace DumpOperation

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


V případě určité operace zobrazí diagnostiku operace, které jsou zpřístupněny aktuálním cílem provedení.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Vstup

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, na kterých daná operace funguje.


### <a name="op--qubit--unit--is-adj"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která se má diagnostikovat



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Příklad

V případě, že je v cíli simulátoru provozu, následující fragment kódu vypíše matici $ $ \begin{aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{Matrix}\right) \end{aligned}.
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a>Poznámky

Volání této operace nemá žádný pozorovatelný účinek v rámci Q #. Přesná diagnostika, která se zobrazí, je-li k, závisí na aktuálním cílovém spuštění a prostředí editoru.
Například při použití v případě simulátoru s plným stavem se zobrazí jednotná matice, která se reprezentuje `op` .

Všimněte si, že při spuštění simulátorů, které připouštějí nejednoznačnost globální fáze (např. simulátor s plným stavem), se můžou vrátit reprezentace, která se může lišit až do globální fáze.

Podobně pořadí reprezentace řádků a sloupců se může lišit od konvencí používaných jednotlivými simulátory podporující tuto operaci.