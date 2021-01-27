---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853423"
---
# <a name="dumpmachine-function"></a>DumpMachine – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vypíše stav aktuálního cílového počítače.

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>Vstup

### <a name="location--t"></a>Umístění: t

Poskytuje informace o tom, kde se má vygenerovat výpis paměti počítače.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

Žádné

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Tato metoda umožňuje vypsat informace o aktuálním stavu cílového počítače do souboru nebo jiného umístění.
Vlastní vygenerované informace a sémantika `location` jsou specifické pro každý cílový počítač. Poskytnutí prázdné řazené kolekce členů jako umístění ( `()` ) nebo pouhého vynechání `location` parametru obvykle znamená, že výstup bude vygenerován do konzoly.

U místních úplných simulátorů distribuovaných jako součást vývojové sady pro plnění stavových prostředí očekává Tato metoda řetězec s cestou k souboru, ve kterém bude zapisovat funkci Wave jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudy pravděpodobnosti měření odpovídajícího stavu.