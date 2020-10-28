---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697888"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery – funkce

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček [](https://nuget.org/packages/)


Pro danou tabulku Pauli operací v daném registru qubits vrátí tato funkce objekt typu `RecoveryFn` , který obsahuje všechny informace potřebné k provedení dekódování vyhledávání tabulky v souvislosti s daným polem Pauli operací.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Vstup

### <a name="table--pauli"></a>Tabulka: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tabulka operací Pauli, které pracují s daným registrem qubit



## <a name="output--recoveryfn"></a>Výstup: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Objekt typu `RecoveryFn` , tj. mapa `Syndrome -> Pauli[]` , která přidruží k danému poli Syndrome odpovídající operaci opravy Pauli.