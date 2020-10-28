---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Uživatelem definovaný typ HTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698693"
---
# <a name="hterm-user-defined-type"></a>Uživatelem definovaný typ HTerm

Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)

Balíček [](https://nuget.org/packages/)


Formát dat předaných z C# na Q #, který představuje období Hamiltonian.
Význam reprezentovaných dat je určen algoritmem, který ho přijímá.

```qsharp

newtype HTerm = (Int[], Double[]);
```

