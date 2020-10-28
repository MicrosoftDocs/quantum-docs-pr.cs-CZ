---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698113"
---
# <a name="dumpregister-function"></a>DumpRegister – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček [](https://nuget.org/packages/)


Vypíše stav aktuálního cílového počítače přidružený k danému qubits.

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="location--t"></a>Umístění: t

Poskytuje informace o tom, kde vygeneruje výpis stavu.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Seznam qubitsů, které se mají ohlásit



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

Žádné

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Tato metoda umožňuje vypsat informace přidružené ke stavu daného qubits do souboru nebo do jiného umístění.
Vlastní vygenerované informace a sémantika `location` jsou specifické pro každý cílový počítač. Poskytnutí prázdné řazené kolekce členů jako umístění ( `()` ) však obvykle znamená, že výstup bude vygenerován do konzoly.

U místních úplných simulátorů distribuovaných jako součást vývojové sady pro plnění stavových prostředí očekává Tato metoda řetězec s cestou k souboru, ve kterém bude zapisovat stav daného qubits (tj. funkce Wave odpovídajícího subsystému) jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudy pravděpodobnosti měření odpovídajícího stavu.
Pokud jsou zadané qubits entangled s jinými qubit a jejich stav nelze oddělit, pouze hlásí, že qubits je entangled.