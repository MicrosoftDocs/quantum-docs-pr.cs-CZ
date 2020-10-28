---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698124"
---
# <a name="dumpmachine-function"></a>DumpMachine – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček [](https://nuget.org/packages/)


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