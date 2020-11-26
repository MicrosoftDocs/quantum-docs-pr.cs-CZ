---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operace DumpOperation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202052"
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



## <a name="remarks"></a>Poznámky

Volání této operace nemá žádný pozorovatelný účinek v rámci Q #. Přesná diagnostika, která se zobrazí, je-li k, závisí na aktuálním cílovém spuštění a prostředí editoru.
Například při použití v případě simulátoru s plným stavem se zobrazí jednotná matice, která se reprezentuje `op` .

Všimněte si, že při spuštění simulátorů, které připouštějí nejednoznačnost globální fáze (např. simulátor s plným stavem), se můžou vrátit reprezentace, která se může lišit až do globální fáze.

Podobně pořadí reprezentace řádků a sloupců se může lišit od konvencí používaných jednotlivými simulátory podporující tuto operaci.