---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220565"
---
# <a name="mostandtail-function"></a>MostAndTail – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí řazenou kolekci členů všech kromě jednoho a posledního elementu pole.

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a>Vstup

### <a name="array--a"></a>pole: ' A []

Pole s alespoň jedním prvkem.



## <a name="output--aa"></a>Výstup: (' A [], ' A)

Řazená kolekce členů všech s výjimkou jednoho a posledního elementu pole.

## <a name="type-parameters"></a>Parametry typu

### <a name="a"></a>A

Typ prvků pole.