---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operace DrawRandomBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853694"
---
# <a name="drawrandombool-operation"></a>Operace DrawRandomBool

Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


S ohledem na pravděpodobnost úspěchu vrátí jednu Bernoulliho zkušební verzi, která je pravdivá s danou pravděpodobností.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Vstup

### <a name="successprobability--double"></a>successProbability: [Double](xref:microsoft.quantum.lang-ref.double)

Pravděpodobnost, se kterou `true` by měla být vrácena.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` s pravděpodobností `successProbability` a `false` s pravděpodobností `1.0 - successProbability` .

## <a name="example"></a>Příklad

Následující ukázky fragmentů kódu Q # přejdou z posunuté mince:

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```