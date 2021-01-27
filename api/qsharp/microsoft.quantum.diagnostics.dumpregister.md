---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829233"
---
# <a name="dumpregister-function"></a>DumpRegister – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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