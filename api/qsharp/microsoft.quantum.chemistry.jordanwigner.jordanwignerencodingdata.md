---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData
title: Uživatelem definovaný typ JordanWignerEncodingData
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerEncodingData
qsharp.summary: Format of data passed from C# to Q# to represent all information for Hamiltonian simulation. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 2acb33c8dab229264273ff23606c47322df740a4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214785"
---
# <a name="jordanwignerencodingdata-user-defined-type"></a>Uživatelem definovaný typ JordanWignerEncodingData

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Formát dat předaných z C# na Q #, který představuje všechny informace pro simulaci Hamiltonian
Význam reprezentovaných dat je určen algoritmem, který ho přijímá.

```qsharp

newtype JordanWignerEncodingData = (Int, Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms, (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), Double);
```

