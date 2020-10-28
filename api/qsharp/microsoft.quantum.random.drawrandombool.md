---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operace DrawRandomBool
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706713"
---
# <a name="drawrandombool-operation"></a>Operace DrawRandomBool

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček [](https://nuget.org/packages/)


S ohledem na pravděpodobnost úspěchu vrátí jednu Bernoulliho zkušební verzi, která je pravdivá s danou pravděpodobností.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Vstup

### <a name="successprobability--double"></a>successProbability: [Double](xref:microsoft.quantum.lang-ref.double)

Pravděpodobnost, se kterou `true` by měla být vrácena.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` s pravděpodobností `successProbability` a `false` s pravděpodobností `1.0 - successProbability` .