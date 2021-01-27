---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856162"
---
# <a name="approximateinputencoder-function"></a>ApproximateInputEncoder – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzhledem k množině koeficientů a tolerance vrátí operaci přípravy stavu, která připraví každý koeficient jako odpovídající amplitudu výpočetního stavu až po danou toleranci.

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Vstup

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerance aproximace, která se má použít při kódování daných koeficientů do vstupního stavu.


### <a name="coefficients--double"></a>koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]

Koeficienty, které mají být zakódovány do vstupního stavu.



## <a name="output--stategenerator"></a>Výstup: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Operace přípravy stavu, která připraví dané koeficienty jako vstupní stav daného registru.