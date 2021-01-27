---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824405"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery – funkce

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pro danou tabulku Pauli operací v daném registru qubits vrátí tato funkce objekt typu `RecoveryFn` , který obsahuje všechny informace potřebné k provedení dekódování vyhledávání tabulky v souvislosti s daným polem Pauli operací.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Vstup

### <a name="table--pauli"></a>Tabulka: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tabulka operací Pauli, které pracují s daným registrem qubit



## <a name="output--recoveryfn"></a>Výstup: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Objekt typu `RecoveryFn` , tj. mapa `Syndrome -> Pauli[]` , která přidruží k danému poli Syndrome odpovídající operaci opravy Pauli.