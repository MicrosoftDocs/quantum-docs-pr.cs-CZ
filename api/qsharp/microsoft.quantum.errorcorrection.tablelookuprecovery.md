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
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="6fa6c-102">TableLookupRecovery – funkce</span><span class="sxs-lookup"><span data-stu-id="6fa6c-102">TableLookupRecovery function</span></span>

<span data-ttu-id="6fa6c-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="6fa6c-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="6fa6c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6fa6c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6fa6c-105">Pro danou tabulku Pauli operací v daném registru qubits vrátí tato funkce objekt typu `RecoveryFn` , který obsahuje všechny informace potřebné k provedení dekódování vyhledávání tabulky v souvislosti s daným polem Pauli operací.</span><span class="sxs-lookup"><span data-stu-id="6fa6c-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="6fa6c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6fa6c-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="6fa6c-107">Tabulka: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="6fa6c-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="6fa6c-108">Tabulka operací Pauli, které pracují s daným registrem qubit</span><span class="sxs-lookup"><span data-stu-id="6fa6c-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="6fa6c-109">Výstup: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="6fa6c-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="6fa6c-110">Objekt typu `RecoveryFn` , tj. mapa `Syndrome -> Pauli[]` , která přidruží k danému poli Syndrome odpovídající operaci opravy Pauli.</span><span class="sxs-lookup"><span data-stu-id="6fa6c-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>