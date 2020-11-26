---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196408"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vrátí počet qubits potřebných ke kódování konkrétního vektoru funkce.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Vstup

### <a name="sample--double"></a>Ukázka: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vzorový vektor funkce, který se má zakódovat do qubit registru.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Velikost potřebnou ke kódování `sample` do qubit registru vyjádřeného jako počet qubits.