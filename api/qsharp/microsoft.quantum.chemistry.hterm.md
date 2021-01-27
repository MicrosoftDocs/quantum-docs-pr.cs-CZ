---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Uživatelem definovaný typ HTerm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 744668a4fe96ee00fe2f7991f4e1f05eea19d417
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851787"
---
# <a name="hterm-user-defined-type"></a>Uživatelem definovaný typ HTerm

Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Formát dat předaných z C# na Q #, který představuje období Hamiltonian.
Význam reprezentovaných dat je určen algoritmem, který ho přijímá.

```qsharp

newtype HTerm = (Int[], Double[]);
```

